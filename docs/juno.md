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
 --website "https://polkachu.com | 0% fee" \
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
  --moniker "polkachu.com | 5% fee" \
  --website "https://polkachu.com" \
  --chain-id uni \
  --from polkachu_test \
  --gas-prices 0.025ujunox
```

If you sync the Juno testnet chain from Block 1, you will start with v1.0.0. If you use Cosmovisor, you will put the v2.0.0-alpha.3 binary in the upgrades/moneta-alpha/bin and v2.0.0-beta.3 in the upgrades/moneta-beta/bin. Cosmovisor will automatically upgrade to the right binary when it reaches the upgrade height.
