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

Create validator

```bash
crescentd tx staking create-validator \
 --amount 10000000ucre \
 --moniker 'polkachu.com' \
 --commission-max-change-rate=0.05 \
 --commission-max-rate=0.10 \
 --commission-rate=0.00 \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com" \
 --pubkey=$(crescentd tendermint show-validator) \
 --chain-id crescent-1 \
 --from polkachu
```

Delegate

```bash
crescentd tx staking delegate crevaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pr37yjn 25000000ucre \
 --chain-id crescent-1 \
 --from polkachu
```
