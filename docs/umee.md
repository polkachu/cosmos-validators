## Umee

create validator

```bash
umeed tx staking create-validator \
    --amount=5000000uumee \
    --commission-max-change-rate=0.05 \
    --commission-max-rate=0.1 \
    --commission-rate=0.02 \
    --min-self-delegation=1 \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --pubkey `umeed tendermint show-validator` \
    --moniker=" polkachu.com" \
    --security-contact="hello@polkachu.com" \
    --chain-id=umee-1 \
    --fees=0.01uumee \
    --from=polkachu
```
