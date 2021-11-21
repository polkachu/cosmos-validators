## General

block height

```bash
watch -n 60 -d "curl -s http://localhost:26657/status | jq -r .result.sync_info.latest_block_height"
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
