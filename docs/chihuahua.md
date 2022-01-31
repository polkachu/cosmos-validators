## Chihuahua

create validator

```bash
chihuahuad tx staking create-validator \
    --amount=1000000000uhuahua \
    --commission-max-change-rate=0.01 \
    --commission-max-rate=0.1 \
    --commission-rate=0.01 \
    --min-self-delegation=1 \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --pubkey `chihuahuad tendermint show-validator` \
    --moniker="polkachu.com | 1% fee" \
    --chain-id=chihuahua-1 \
    --security-contact="hello@polkachu.com" \
    --from=polkachu
```

Edit validator

```bash
chihuahuad tx staking edit-validator \
    --moniker="  polkachu.com" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Please consider delegating to Polkachu validators on Akash, Juno, SifChain, Kava, BitCanna, and KiChain. Contact: hello@polkachu.com" \
    --chain-id=chihuahua-1 \
    --from=polkachu
```
