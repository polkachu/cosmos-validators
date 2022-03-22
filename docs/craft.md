## Lum Network

create validator

```bash
craftd gentx craft_test 1000000uexp \
    --home="$HOME/.craftd/" \
    --keyring-backend=os \
    --chain-id=craft-testnet-1 \
    --moniker="polkachu.com" \
    --commission-max-change-rate "0.05" \
    --commission-max-rate "0.10" \
    --commission-rate "0.05" \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com"
```
