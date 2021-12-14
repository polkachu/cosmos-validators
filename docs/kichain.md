## Kichain

create validator

```bash
kid tx staking create-validator \
    --amount=5000000uxki \
    --commission-max-change-rate=0.01 \
    --commission-max-rate=0.1 \
    --commission-rate=0 \
    --min-self-delegation=1 \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --pubkey `kid tendermint show-validator` \
    --moniker="polkachu.com | 0% fee" \
    --chain-id=kichain-2 \
    --gas-prices=0.025uxki \
    --from=polkachu
```

Delegate

```bash
kid tx staking delegate kivaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pq8jud7 70000000uxki \
    --chain-id=kichain-2 \
    --gas-prices=0.025uxki \
    --from=polkachu
```

```bash
kid tx staking edit-validator \
    --commission-rate="0.05" \
    --moniker="polkachu.com | 5% fee" \
    --chain-id=kichain-2 \
    --gas-prices=0.025uxki \
    --from=polkachu
```

Claim rewards

```bash
kid tx distribution withdraw-all-rewards \
    --chain-id=kichain-2 \
    --gas-prices=0.025uxki \
    --from=polkachu
```
