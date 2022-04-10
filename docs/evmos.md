## Evmos

Claim rewards

```bash
evmosd tx distribution withdraw-rewards evmosvaloper125fkz3mq6qxxpkmphdl3ep92t0d3y969xmt8hz --commission --from=polkachu
```

Delegate

```bash
evmosd tx staking delegate evmosvaloper125fkz3mq6qxxpkmphdl3ep92t0d3y969xmt8hz 1000000aevmos \
 --from polkachu
```

Testnet

Create validator

```bash
evmosd tx staking create-validator \
  --amount=2000000000000000000atevmos \
  --pubkey=$(evmosd tendermint show-validator) \
 --commission-max-change-rate "0.05" \
 --commission-max-rate "0.10" \
 --commission-rate "0.05" \
 --min-self-delegation "1" \
 --moniker "polkachu.com" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
  --gas="auto" \
  --gas-prices="0.025atevmos" \
   --gas-adjustment="1.5" \
  --from=evmos_test
```

Edit validator

```bash
evmosd tx staking edit-validator \
 --moniker "polkachu.com" \
 --website "https://polkachu.com" \
  --gas="auto" \
  --gas-prices="0.025atevmos" \
   --gas-adjustment="1.5" \
  --from=evmos_test
```
