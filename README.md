# Substrate-based Validator Node Ansible Setup

```bash
watch -n 60 -d "curl -s http://localhost:26657/status | jq -r .result.sync_info.latest_block_height"
curl -s localhost:26657/net_info | jq -r .result.peers[].node_info.moniker
journalctl -u cosmovisor.service -f | grep "committed"
systemctl status cosmovisor
curl -s localhost:26657/net_info | jq -r '.result.peers[] | .node_info.moniker, .node_info.id, .node_info.listen_addr, .remote_ip'
curl -s localhost:26657/net_info | jq -r .result.peers[].node_info.moniker
watch -n 2 "  curl -s localhost:26657/net_info | jq -r '.result.n_peers'"
```
