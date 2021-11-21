## Sifchain

Create validator

```bash
sifnoded tx staking create-validator \
 --amount 1000000000000000000000rowan \
 --commission-max-change-rate "0.01" \
 --commission-rate "0.02" \
 --commission-max-rate "0.1" \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --pubkey=$(sifnoded tendermint show-validator) \
 --moniker 'Polkachu' \
 --chain-id sifchain-1 \
 --gas-adjustment="1.5" \
 --gas="200000" \
 --fees 100000000000000000rowan \
 --from polkachu
```

Delegate

```bash
sifnoded tx staking delegate sifvaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pfj2j90 420000000000000000000rowan \
 --chain-id sifchain-1 \
 --from=polkachu \
 --gas-adjustment="1.5" \
 --gas="200000" \
 --fees 100000000000000000rowan
```
