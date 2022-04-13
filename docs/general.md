## General

block height

```bash
watch -n 60 -d "curl -s http://localhost:26657/status | jq -r .result.sync_info.latest_block_height"
```

Check if the chain has synced

```bash
curl http://localhost:26657/status | jq .result.sync_info.catching_up
```

List Connected Peers

```bash
curl -s localhost:26657/net_info | jq -r '.result.peers[] | .node_info.moniker, .node_info.id, .node_info.listen_addr, .remote_ip'
```

Check Consensus Vote

```bash
watch -n 0.08 "curl -s localhost:26657/status | jq -r .result.sync_info.latest_block_height; curl -s localhost:26657/consensus_state | jq -r '.result.round_state.height_vote_set[0] | (.prevotes_bit_array, .precommits_bit_array)'"
```

Get Peer Info

```bash
echo "$(BINARY tendermint show-node-id)@$(curl ifconfig.me):26656"
```

Compile Peers from a line-breaker list to a comma-delimited list (Cerberus example)

```bash
PEERS=$(curl https://raw.githubusercontent.com/cerberus-zone/cerberus/main/networks/mainnet/peers.txt | head -n 10 | sed 's/$/,/' | tr -d '\n' | sed '$ s/.$//'); sed "s/persistent_peers = \"\"/persistent_peers = $PEERS/" ~/.cerberusd/config/config.toml -i
```

Get all delegations to a validator

```bash
BINARY q staking delegations-to VALIDATOR_ADDRESS -o json | jq '.delegation_responses[].delegation | { addr: .delegator_address, shares: (.shares | tonumber| floor / 1000000)}' | jq -c -s 'sort_by(.shares) | .[]'
```

Get a list of all validators sorted by their voting powers

```bash
BINARY query staking validators --limit 1000 -o json | jq -r '.validators[] | select(.status=="BOND_STATUS_BONDED") | [ (.tokens|tonumber / pow(10; 6)), .description.moniker ] | @csv' | column -t -s"," | sort -k1 -n -r | nl
```

Get a list of all validators sorted by their voting powers (another way)

```bash
BINARY --node https://rpc.sifchain.finance:443 query staking validators --limit 1000 -o json | jq -r '.validators[] | [.operator_address, .status, (.tokens|tonumber / pow(10; 6)), .description.moniker] | @csv' | column -t -s"," | sort -k3 -n -r | nl
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

Send token through IBC

```bash
BINARY tx ibc-transfer transfer transfer channel-x <destination_address> 1denom --from xxx --gas xxx
```
