## Agoric

create validator

```bash
ag0 tx staking create-validator \
  --amount=980000ubld \
  --pubkey=$(ag0 tendermint show-validator) \
  --moniker=" polkachu.com" \
  --website "https://polkachu.com" \
  --identity "0A6AF02D1557E5B4" \
  --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
  --commission-rate="0.01" \
  --commission-max-rate="0.10" \
  --commission-max-change-rate="0.05" \
  --min-self-delegation="1" \
  --from=polkachu \
  --chain-id=agoric-3
```
