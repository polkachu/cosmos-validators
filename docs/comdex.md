## Comdex

create validator

```bash
comdex tx staking create-validator \
 --amount 10000000ucmdx \
 --commission-max-change-rate "0.01" \
 --commission-max-rate "0.10" \
 --commission-rate "0" \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --pubkey=$(comdex tendermint show-validator) \
 --moniker 'polkachu.com | 0% fee' \
 --chain-id comdex-1 \
 --fees=5000ucmdx \
 --from polkachu
```

Delegate

```bash
comdex tx staking delegate comdexvaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4p3447dz 190000000ucmdx \
    --chain-id=comdex-1 \
    --fees=5000ucmdx \
    --from=polkachu
```

Edit validator

```bash
comdex tx staking edit-validator \
    --moniker 'polkachu.com | 2% fee' \
    --chain-id=comdex-1 \
    --fees=5000ucmdx \
    --from=polkachu
```

Redelegate

```bash
comdex tx staking redelegate <old> <new> 1000000000000000ucmdx \
    --chain-id=comdex-1 \
    --fees=10000ucmdx \
    --gas=auto \
    --gas-adjustment="1.5" \
    --from=polkachu
```

## Testnet

```bash
comdex tx staking create-validator \
 --amount 24000000000ucmdx \
 --commission-max-change-rate "0.1" \
 --commission-max-rate "0.20" \
 --commission-rate "0.10" \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --pubkey=$(comdex tendermint show-validator) \
 --moniker 'polkachu.com' \
 --chain-id comets-test \
 --fees=40000ucmdx \
 --from comdex_test \
 --node http://localhost:39657
```
