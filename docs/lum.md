## Lum Network

create validator

```bash
lumd tx staking create-validator \
    --amount=1000000ulum \
    --pubkey=$(lumd tendermint show-validator) \
    --moniker="polkachu.com" \
    --commission-max-change-rate "0.01" \
    --commission-max-rate "0.10" \
    --commission-rate "0" \
    --min-self-delegation="1" \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --chain-id=lum-network-1
    --from polkachu
```

Delegate

```bash
lumd tx staking edit-validator \
   --details="Something something" \
   --chain-id=lum-network-1
   --from polkachu
```
