## Fetch

Create Validator

```bash
fetchd tx staking create-validator \
  --amount=278000000000000000000afet \
  --pubkey=$(fetchd tendermint show-validator) \
    --moniker='polkachu.com' \
    --website "https://polkachu.com" \
    --moniker='polkachu.com' \
    --identity "0A6AF02D1557E5B4" \
    --security-contact "hello@polkachu.com" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
  --commission-rate="0" \
  --commission-max-rate="0.10" \
  --commission-max-change-rate="0.05" \
    --min-self-delegation=1 \
   --from=polkachu
```
