## Cosmic Horizon

create validator

```bash
cohod tx staking create-validator \
  --amount=19000000ucoho \
  --pubkey=$(cohod tendermint show-validator) \
  --moniker="polkachu-coho-testnet" \
  --moniker=" polkachu.com" \
  --website "https://polkachu.com" \
  --identity "0A6AF02D1557E5B4" \
  --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
  --security-contact "hello@polkachu.com"  \
  --chain-id=darkmatter-1 \
  --commission-rate="0.10" \
  --commission-max-rate="0.20" \
  --commission-max-change-rate="0.10" \
  --min-self-delegation="1" \
  --fees 2000ucoho \
  --from=coho_test
```
