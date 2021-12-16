## Juno

### Mainnet

create validator

```bash
junod tx staking create-validator \
 --amount 9000000ujuno \
 --commission-max-change-rate "0.01" \
 --commission-max-rate "0.10" \
 --commission-rate "0" \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --pubkey=$(junod tendermint show-validator) \
 --moniker 'polkachu.com' \
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

Get Rewards

```bash
junod tx distribution withdraw-rewards junovaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pvzc6k3  \
  --commission \
  --from polkachu  \
  --gas-prices 0.025ujuno
```

Delegate

```bash
junod tx staking delegate junovaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pvzc6k3 6000000ujuno \
  --from polkachu  \
  --gas-prices 0.025ujuno
```

### Testnet

create validator

```bash
junod tx staking create-validator \
 --amount 2000000ujunox \
 --commission-max-change-rate "0.01" \
 --commission-max-rate "0.10" \
 --commission-rate "0.05" \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --pubkey=$(junod tendermint show-validator) \
 --moniker 'Polkachu' \
 --chain-id uni \
 --gas-prices 0.025ujunox \
 --from polkachu_test
```

Edit validator

```bash
junod tx staking edit-validator \
  --moniker "polkachu.com | test" \
  --chain-id uni \
  --from juno_test \
  --gas-prices 0.025ujunox
```
