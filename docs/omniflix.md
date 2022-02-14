## Omniflix

create validator

```bash
omniflixhubd tx staking create-validator \
  --amount=199000000uflix \
  --pubkey=$(omniflixhubd tendermint show-validator) \
  --moniker=" polkachu.com" \
  --website "https://polkachu.com" \
  --identity "0A6AF02D1557E5B4" \
  --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
  --security-contact="hello@polkachu.com" \
  --chain-id="flixnet-3" \
  --commission-rate="0.10" \
  --commission-max-rate="0.20" \
  --commission-max-change-rate="0.10" \
  --min-self-delegation="1" \
  --gas="auto" \
  --gas-adjustment="1.2" \
  --gas-prices="0.001uflix" \
  --from=omniflix_test
```

create validator

```bash
omniflixhubd tx staking delegate omniflixvaloper1jt9w26mpxxjsk63mvd4m2ynj0af09cslnda7l8 180000000uflix \
  --chain-id="flixnet-3" \
  --gas="auto" \
  --gas-adjustment="1.2" \
  --gas-prices="0.001uflix" \
  --from=polkachu
```
