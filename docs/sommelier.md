## Sommelier

create validator

```bash
sommelier tx staking create-validator \
  --amount=1000000usomm \
  --pubkey=$(sommelier tendermint show-validator) \
  --moniker="polkachu.com" \
  --website "https://polkachu.com" \
  --identity "0A6AF02D1557E5B4" \
  --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
  --chain-id="sommelier-3" \
  --commission-rate="0.10" \
  --commission-max-rate="0.20" \
  --commission-max-change-rate="0.01" \
  --min-self-delegation="1" \
  --gas=300000 \
  --fees="0usomm" \
  --from=polkachu
```

Edit validator

```bash
sommelier tx staking edit-validator \
  --commission-rate="0.07" \
  --moniker="polkachu.com" \
  --gas=300000 \
  --fees="0usomm" \
  --chain-id="sommelier-3" \
  --from=polkachu
```
