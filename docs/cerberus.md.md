## Agoric

create validator

```bash
cerberusd tx staking create-validator \
  --amount=10000000000000ucrbrus \
  --pubkey=$(cerberusd tendermint show-validator) \
  --moniker="polkachu.com" \
  --website "https://polkachu.com" \
  --identity "0A6AF02D1557E5B4" \
  --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
  --commission-rate="0.10" \
  --commission-max-rate="0.20" \
  --commission-max-change-rate="0.05" \
  --security-contact="hello@polkachu.com" \
  --min-self-delegation="1" \
  --from=cerberus_test
```
