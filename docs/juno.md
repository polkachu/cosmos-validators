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

Get Rewards

```bash
junod tx distribution withdraw-rewards junovaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pvzc6k3  \
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

junod tx wasm store cw_erc20.wasm --from polkachu_test --chain-id=uni --gas auto --gas-prices 0.025ujunox

CODE_ID=$(junod query tx B83682FF5AA4118A09F8E39E4422FF4AA544FAB2B73E6F939F3EA1A6D554D235 --output json | jq -r '.logs[0].events[-1].attributes[0].value')

If you sync the Juno testnet chain from Block 1, you will start with v1.0.0. If you use Cosmovisor, you will put the v2.0.0-alpha.3 binary in the upgrades/moneta-alpha/bin and v2.0.0-beta.3 in the upgrades/moneta-beta/bin. Cosmovisor will automatically upgrade to the right binary when it reaches the upgrade height.
