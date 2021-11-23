## Kava

create validator

```bash
kvcli tx staking create-validator \
    --amount=2000000ukava \
    --min-self-delegation "1" \
    --moniker 'polkachu.com | 0% fee' \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --pubkey=$(kvd tendermint show-validator) \
    --commission-max-change-rate "0.01" \
    --commission-max-rate "0.10" \
    --commission-rate "0" \
    --min-self-delegation="1" \
    --from=polkachu \
    --chain-id=kava-8 \
    --fees=2000ukava \
    --gas=auto \
    --gas-adjustment=1.4
```
