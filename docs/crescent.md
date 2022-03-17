## Cerberus

GenTx

```bash
crescentd add-genesis-account $(crescentd keys show crescent_test -a) 1000000ucre
```

```bash
crescentd gentx crescent_test 1000000ucre --chain-id mooncat-1-1 \
 --moniker 'polkachu.com' \
 --commission-max-change-rate=0.05 \
 --commission-max-rate=0.20 \
 --commission-rate=0.05 \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com" \
 --pubkey=$(crescentd tendermint show-validator)
```
