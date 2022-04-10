## Certik

create validator

```bash
gaiad tx staking create-validator \
    --amount=1000000uatom \
    --commission-max-change-rate=0.01 \
    --commission-max-rate=0.10 \
    --commission-rate=0.05 \
    --min-self-delegation 1 \
    --pubkey=$(gaiad tendermint show-validator) \
    --moniker 'polkachu.com' \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --security-contact="hello@polkachu.com" \
    --chain-id=cosmoshub-4 \
    --gas="auto" \
    --gas-prices="0.0025uatom" \
    --gas-adjustment 1.5 \
    --from=polkachu
```

```bash
gaiad tx staking edit-validator cosmosvaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pqeemx8 \
    --commission-rate=0.04 \
    --moniker ' polkachu.com' \
    --chain-id=cosmoshub-4 \
    --gas="auto" \
    --gas-prices="0.0025uatom" \
    --gas-adjustment 1.5 \
    --from=polkachu
```
