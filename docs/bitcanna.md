## BitCanna

create validator

```bash
bcnad tx staking create-validator \
 --amount 1000000ubcna \
 --commission-max-change-rate "0.01" \
 --commission-max-rate "0.10" \
 --commission-rate "0" \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --pubkey=$(bcnad tendermint show-validator) \
 --moniker '🌿 polkachu.com | 0% fee 🌿' \
 --security-contact="hello@polkachu.com" \
 --chain-id bitcanna-1 \
 --gas auto \
 --gas-adjustment 1.5 \
 --gas-prices 0.001ubcna \
 --from polkachu
```

Delegate

```bash
bcnad tx staking delegate bcnavaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pxqv0cj 41000000ubcna \
 --chain-id bitcanna-1 \
 --gas auto \
 --gas-adjustment 1.5 \
 --gas-prices 0.001ubcna \
 --from polkachu
```

## BitCanna Testnet

```bash
bcnad tx staking create-validator \
 --amount 1000000ubcna \
 --commission-max-change-rate 0.10 \
 --commission-max-rate 0.2 \
 --commission-rate 0.1 \
 --from bitcanna_test \
 --min-self-delegation 1 \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --pubkey=$(bcnad tendermint show-validator) \
 --moniker 'polkachu.com' \
 --security-contact="hello@polkachu.com" \
 --chain-id bitcanna-dev-3 \
 --gas auto \
 --gas-adjustment 1.5 \
 --gas-prices 0.001ubcna
```

```bash
bcnad tx staking delegate bcnavaloper1jt9w26mpxxjsk63mvd4m2ynj0af09cslqvl8mh 500000000ubcna \
 --chain-id bitcanna-dev-3 \
 --gas auto \
 --gas-adjustment 1.5 \
 --gas-prices 0.001ubcna \
 --from bitcanna_test
```
