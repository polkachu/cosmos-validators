# Substrate-based Validator Node Ansible Setup

```bash
watch -n 60 -d "curl -s http://localhost:26657/status | jq -r .result.sync_info.latest_block_height"
curl -s localhost:26657/net_info | jq -r .result.peers[].node_info.moniker
journalctl -u cosmovisor.service -f | grep "committed"
systemctl status cosmovisor
curl -s localhost:26657/net_info | jq -r '.result.peers[] | .node_info.moniker, .node_info.id, .node_info.listen_addr, .remote_ip'
curl -s localhost:26657/net_info | jq -r .result.peers[].node_info.moniker
watch -n 2 "  curl -s localhost:26657/net_info | jq -r '.result.n_peers'"d
```

Here is something

```bash
c12726cfc959b54c90c0831216bab970645b536c@18.223.79.98:26656,b1f46f1a1955fc773d3b73180179b0e0a07adce1@162.55.244.250:39656,7f593757c0cde8972ce9
29381d8ac8e446837811@178.18.255.244:26656,7b22dfc605989d66b89d2dfe118d799ea5abc2f0@167.99.210.65:26656,4bd9cac019775047d27f9b9cea66b25270ab497d@137.184.7.164:2665
6,bd822a8057902fbc80fd9135e335f0dfefa32342@65.21.202.159:38656,15827c6c13f919e4d9c11bcca23dff4e3e79b1b8@51.38.52.210:38656,e665df28999b2b7b40cff2fe4030682c380bf29
4@188.40.106.109:38656,92804ce50c85ff4c7cf149d347dd880fc3735bf4@34.94.231.154:26656,795ed214b8354e8468f46d1bbbf6e128a88fe3bd@34.127.19.222:26656,ea9c1ac0e91639b2c
7957d9604655e2263abe4e1@185.181.103.136:26656
```
