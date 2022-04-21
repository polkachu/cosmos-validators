# Defund

create validator

```bash
defundd tx staking create-validator \
  --amount=1000000ufetf \
  --pubkey=$(defundd tendermint show-validator) \
 --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --pubkey="$(defundd tendermint show-validator)" \
    --moniker 'polkachu.com' \
    --chain-id="akashnet-2" \
    --commission-rate="0.01" \
    --commission-max-rate="0.10" \
    --commission-max-change-rate="0.05" \
    --min-self-delegation="1" \
  --chain-id=defund-private-1 \
  --gas="auto" \
  --from=defund_test
```

Delegate

```bash
defundd tx staking delegate defundvaloper1jt9w26mpxxjsk63mvd4m2ynj0af09cslzrg9vj 23000000ufetf \
  --gas="auto" \
   --gas-prices 0.025ufetf \
   --gas-adjustment 1.5 \
 --from defund_test

```
