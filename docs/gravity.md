## Umee

Create Validator

```bash
gravity tx staking create-validator \
 --amount=1000000ugraviton \
 --pubkey=$(gravity tendermint show-validator) \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --moniker=" polkachu.com" \
 --security-contact="hello@polkachu.com" \
 --chain-id=gravity-bridge-3 \
 --from=polkachu \
 --commission-rate="0.05" \
 --commission-max-rate="0.10" \
 --commission-max-change-rate="0.05" \
 --gas=auto \
 --min-self-delegation="1" \
 --gas-adjustment=1.4
```

Delegate gravity

```bash
gravity tx staking delegate gravityvaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pskxg9g 1000000ugraviton \
 --chain-id=gravity-bridge-3 \
 --from polkachu
```

Configure gravity

```bash
gravity tx gravity set-orchestrator-address gravityvaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pskxg9g gravity1y0yvuwnk7g3at6yvl6ctgsvzuxaeqjkwuakeg7 0x99E43230eCec926a7FFc2E4CD22153494D5a84a3 --from polkachu --chain-id gravity-bridge-3
```
