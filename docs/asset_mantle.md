## Agoric

Create Validator

```bash
mantleNode tx staking create-validator \
    --amount=6000000000umntl \
    --pubkey=$(mantleNode tendermint show-validator) \
    --website "https://polkachu.com" \
    --moniker='polkachu.com' \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --chain-id='mantle-1' \
    --commission-max-change-rate=0.05 \
    --commission-max-rate=0.1 \
    --commission-rate=0 \
    --min-self-delegation=1 \
    --from=polkachu
```

Delegate

```bash
mantleNode tx staking delegate mantlevaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pmkjlwt 500000000umntl \
 --from polkachu
```
