## Cerberus

GenTx

```bash
cerberusd gentx polkachu 4000000000000ucrbrus \
--chain-id cerberus-chain-1 \
 --moniker 'polkachu.com' \
 --commission-max-change-rate=0.05 \
 --commission-max-rate=0.20 \
 --commission-rate=0.05 \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com"
```

Edit validator

```bash
cerberusd tx staking edit-validator \
  --moniker="polkachu.com | Delegate beyond top 10" \
  --details "Please delegate beyond top 10 validators for decentralization. Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
  --chain-id cerberus-chain-1 \
  --from=polkachu
```
