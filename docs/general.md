## General

block height

```bash
watch -n 60 -d "curl -s http://localhost:26657/status | jq -r .result.sync_info.latest_block_height"
```

Check if the chain has synced

```bash
curl http://localhost:26657/status | jq .result.sync_info.catching_up
```

Connected Peers

```bash
curl -s localhost:26657/net_info | jq -r '.result.peers[] | .node_info.moniker, .node_info.id, .node_info.listen_addr, .remote_ip'
```

Check consensus vote

```bash
watch -n 0.08 "curl -s localhost:26657/status | jq -r .result.sync_info.latest_block_height; curl -s localhost:26657/consensus_state | jq -r '.result.round_state.height_vote_set[0] | (.prevotes_bit_array, .precommits_bit_array)'"
```

Get Peer

```bash
echo "$(BINARY tendermint show-node-id)@$(curl ifconfig.me):26656"
```

Check logs and cosmovisor status

```bash
journalctl -u cosmovisor.service -f
journalctl -u cosmovisor.service -f | grep "committed"
systemctl status cosmovisor
```

Check if the node is performing fine:

```bash
BINARY query slashing signing-infos --output json | jq | grep <valcons_address>
```
