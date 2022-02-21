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
    --fees=200uumee \
    --from=polkachu
```

Configure peggo

```bash
umeed tx gravity set-orchestrator-address umeevaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4phlh7lv umee1xrrfek3qpz4ja8ccrjklfy064asyqq9kpytssa 0x99E43230eCec926a7FFc2E4CD22153494D5a84a3 --chain-id="umee-1" --from=polkachu --fees=200uumee
```
