## Chain

GenTx

```bash
BINARY gentx polkachu AMOUNT \
 --chain-id CHAIN_ID \
 --moniker 'polkachu.com' \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com"
 --commission-max-change-rate=0.05 \
 --commission-max-rate=0.10 \
 --commission-rate=0.01
```

Create validator

```bash
BINARY tx staking create-validator \
 --amount AMOUNT \
 --commission-max-change-rate "0.05" \
 --commission-max-rate "0.10" \
 --commission-rate "0.01" \
 --min-self-delegation "1" \
 --pubkey=$(BINARY tendermint show-validator) \
 --moniker ' polkachu.com' \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com"
 --chain-id CHAIN_ID \
 --SOME-EXTRA \
 --from polkachu
```

galaxyd tx staking create-validator \
 --amount 3000000000uglx \
 --commission-max-change-rate "0.05" \
 --commission-max-rate "0.10" \
 --commission-rate "0.01" \
 --min-self-delegation "1" \
 --pubkey=$(galaxyd tendermint show-validator) \
 --moniker ' polkachu.com' \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com" \
 --chain-id galaxy-1 \
 --from polkachu
