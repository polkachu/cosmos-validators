## Certik

create validator

```bash
certik tx staking create-validator \
 --amount 2000000uctk \
 --moniker ' polkachu.com | 0% fee' \
 --commission-max-change-rate=0.01 \
 --commission-max-rate=0.10 \
 --commission-rate=0.05 \
 --min-self-delegation 1 \
 --pubkey=$(certik tendermint show-validator) \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com" \
 --chain-id shentu-2.2 \
 --from polkachu
```

Edit

```bash
certik tx staking edit-validator \
 --moniker ' polkachu.com' \
 --chain-id shentu-2.2 \
 --from polkachu
```

Delegate

```bash
certik tx staking delegate certikvaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4p434ez9 2000000uctk \
 --chain-id shentu-2.2 \
 --from=polkachu
```
