## Certik

create validator

```bash
memed tx staking create-validator \
--pubkey=$(memed tendermint show-validator) \
 --chain-id meme-1 \
--amount=1000000umeme \
 --commission-max-change-rate=0.01 \
 --commission-max-rate=0.10 \
 --commission-rate=0.05 \
 --min-self-delegation 1 \
  --moniker 'polkachu.com' \
 --pubkey=$(memed tendermint show-validator) \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com" \
--gas-prices=0.025umeme \
--from=polkachu
```
