## Deweb Testnet

create validator

```bash
dewebd tx staking create-validator \
    --amount 1000000udws \
    --pubkey $(dewebd tendermint show-validator) \
    --moniker="polkachu.com" \
    --commission-max-change-rate 0.10 \
    --commission-max-rate 0.2 \
    --commission-rate 0.1 \
    --min-self-delegation="1" \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --security-contact "hello@polkachu.com" \
    --chain-id deweb-testnet-0 \
    --gas auto \
    --gas-adjustment 1.5 \
    --gas-prices 0.001udws \
    --from deweb_test
```

Withdraw rewards

```bash
dewebd tx distribution withdraw-rewards dewebvaloper1jt9w26mpxxjsk63mvd4m2ynj0af09cslwkjylp --commission \
 --chain-id deweb-testnet-0 \
 --gas auto \
 --gas-adjustment 1.5 \
 --gas-prices 0.001udws \
 --from deweb_test
```

Delegate

```bash
dewebd tx staking delegate dewebvaloper1jt9w26mpxxjsk63mvd4m2ynj0af09cslwkjylp 113000000udws \
 --chain-id deweb-testnet-0 \
 --gas auto \
 --gas-adjustment 1.5 \
 --gas-prices 0.001udws \
 --from deweb_test
```
