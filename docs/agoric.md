## Agoric

create validator

```bash
agd tx staking create-validator \
  --amount=50000000ubld \
  --broadcast-mode=block \
  --pubkey=$(agd tendermint show-validator) \
  --moniker="polkachu"
  --website "https://polkachu.com" \
  --identity "0A6AF02D1557E5B4" \
  --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
  --commission-rate="0.10" \
  --commission-max-rate="0.20" \
  --commission-max-change-rate="0.01" \
  --min-self-delegation="1" \
  --from=polkachu \
  --chain-id=agoricdev-6 \
  --gas=auto \
  --gas-adjustment=1.4
```

Edit validator

```bash
agd tx staking edit-validator \
  --moniker="polkachu.com" \
  --from=polkachu \
  --chain-id=agoricdev-6 \
  --gas=auto \
  --gas-adjustment=1.4
```

Delegate

```bash
agd tx staking delegate agoricvaloper1l0ac26xx3c4mhewtcwxmxxxsvy8xc7u974pefk 10000000ubld \
  --from=polkachu \
  --chain-id=agoricdev-6 \
  --gas=auto \
  --gas-adjustment=1.4
```

Unjail

```bash
agd tx slashing unjail --from agoric1l0ac26xx3c4mhewtcwxmxxxsvy8xc7u9wdjs4h --chain-id=agoricdev-6
```
