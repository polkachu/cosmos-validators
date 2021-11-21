## Juno

create validator

```bash
junod tx staking create-validator \
 --amount 9000000ujuno \
 --commission-max-change-rate "0.01" \
 --commission-max-rate "0.10" \
 --commission-rate "0.0069" \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --pubkey=$(junod tendermint show-validator) \
 --moniker 'Polkachu' \
 --chain-id juno-1 \
 --gas-prices 0.025ujuno \
 --from polkachu
```

Delegate

```bash
junod tx staking delegate junovaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pvzc6k3 33000000ujuno \
 --chain-id juno-1 \
 --from=polkachu \
 --gas-prices 0.025ujuno
```

Edit validator

```bash
junod tx staking edit-validator \
  --moniker "polkachu.com" \
  --chain-id juno-1 \
  --from polkachu \
  --gas-prices 0.025ujuno
```
