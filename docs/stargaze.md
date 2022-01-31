## Stargaze

create validator

```bash
starsd tx staking create-validator \
    --amount=1000000ustars \
    --commission-rate="0.05" \
    --commission-max-rate="0.1" \
    --commission-max-change-rate="0.05" \
    --min-self-delegation="1" \
    --pubkey=$(starsd tendermint show-validator) \
    --moniker="polkachu.com" \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --chain-id=stargaze-1 \
    --from=polkachu
```

Edit validator

```bash
starsd tx staking edit-validator \
    --moniker "polkachu.com" \
    --chain-id=stargaze-1 \
    --from=polkachu
```
