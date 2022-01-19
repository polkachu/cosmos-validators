## Kava

create validator

```bash
kava tx staking create-validator \
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
    --chain-id=kava-9 \
    --fees=2000ukava \
    --gas=auto \
    --gas-adjustment=1.4
```

Delegate

```bash
kava tx staking delegate kavavaloper125s8t5c6ypwee7ytun90lnhgpls2zl3vta43aj 483000000ukava \
    --from=polkachu \
    --chain-id=kava-9 \
    --fees=2000ukava \
    --gas=auto \
    --gas-adjustment=1.4
```
