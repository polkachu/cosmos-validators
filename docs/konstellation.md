## Konstellation BetaNet

create validator

```bash
knstld tx staking create-validator \
    --amount 1000000udarc \
    --pubkey $(knstld tendermint show-validator) \
    --moniker="polkachu.com" \
    --commission-max-change-rate 0.10 \
    --commission-max-rate 0.2 \
    --commission-rate 0.1 \
    --min-self-delegation="1" \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --security-contact "hello@polkachu.com" \
    --chain-id darchub \
    --from=konstellation_test \
    --fees=2udarc
```

Edit validator

```bash
knstld tx staking edit-validator \
    --moniker=" polkachu.com" \
    --commission-rate 0.01 \
    --chain-id darchub \
    --fees=20udarc \
    --from=polkachu_test
```
