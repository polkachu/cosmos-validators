## Akash

create validator

```bash
akash tx staking create-validator \
    --amount=1000000uakt \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --pubkey="$(akash tendermint show-validator)" \
    --moniker 'polkachu.com | 0% fee' \
    --chain-id="akashnet-2" \
    --commission-rate="0" \
    --commission-max-rate="0.10" \
    --commission-max-change-rate="0.05" \
    --min-self-delegation="1" \
    --gas="auto" \
    --gas-adjustment 1.15 \
    --gas-prices="0.025uakt" \
    --from=polkachu
```

Edit validator

```bash
akash tx staking edit-validator \
    --website "https://polkachu.com" \
    --moniker 'polkachu.com | 0% fee' \
    --security-contact "hello@polkachu.com" \
    --chain-id="akashnet-2" \
    --gas="auto" \
    --gas-adjustment 1.3 \
    --gas-prices="0.03uakt" \
    --from=polkachu
```
