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

```
junod tx staking create-validator \
  --amount 6000000ujunox \
  --commission-max-change-rate "0.1" \
  --commission-max-rate "0.20" \
  --commission-rate "0.1" \
  --min-self-delegation "1" \
  --details "This is my validator" \
  --pubkey=$(junod tendermint show-validator) \
  --moniker '[Polkachu] 1% fee' \
  --chain-id  uni \
  --gas-prices 0.025ujunox \
  --from polkachu
```

junod tx staking edit-validator --website="https://polkachu.com" --from=polkachu --gas-prices="0.025ujunox" --chain-id=uni
junod tx staking delegate junovaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pvzc6k3 1390000ujunox --chain-id=uni --from=polkachu --gas-prices="0.025ujunox"
