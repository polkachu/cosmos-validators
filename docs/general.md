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

Check logs and cosmovisor status

```bash
journalctl -u cosmovisor.service -f
journalctl -u cosmovisor.service -f | grep "committed"
systemctl status cosmovisor
```

Check if the node is performing fine:

```bash
bcnad query slashing signing-infos --output json | jq | grep bcnavalcons1gp957czryfgyvxwn3tfnyy2f0t9g2p4pjnln5n
```
