## Chain

GenTx

```bash
seid gentx sei_test 1000000usei \
 --chain-id atlantic-1 \
 --moniker 'polkachu.com' \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com" \
 --commission-max-change-rate=0.05 \
 --commission-max-rate=0.10 \
 --commission-rate=0.05
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

```bash
chaind tx staking create-validator --yes \
 --amount 1000000000000tkyve \
 --pubkey=$(chaind tendermint show-validator) \
 --chain-id korellia \
 --from kyve_test \
 --commission-max-change-rate "0.05" \
 --commission-max-rate "0.20" \
 --commission-rate "0.10" \
 --min-self-delegation "1" \
 --moniker 'polkachu.com' \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com" \
--gas auto \
--gas-adjustment 1.5 \
--gas-prices 0.001udws \
--broadcast-mode block
```

```bash
chihuahuad tx staking create-validator \
 --amount="100000000stake" \
 --pubkey=$(chihuahuad tendermint show-validator) \
 --chain-id="chitestnet-1" \
 --from="chihuahua_test" \
 --node="http://localhost:29657" \
--commission-max-change-rate "0.05" \
 --commission-max-rate "0.10" \
 --commission-rate "0.05" \
 --min-self-delegation "1" \
 --moniker "polkachu.com" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact "hello@polkachu.com"
```

```bash
chaind tx staking delegate kyvevaloper1jt9w26mpxxjsk63mvd4m2ynj0af09cslxlnsvh 1350000000000tkyve \
--from kyve_test
```

echelond tx staking create-validator --amount=1000000000000000000000000aechelon --pubkey=$(echelond tendermint show-validator) --moniker="" --from=<echelonaddress> --min-self-delegation="1" --commission-max-change-rate="0.01" --commission-max-rate="0.20" --commission-rate="0.05" --chain-id=echelon_3000-3

strided tx staking create-validator \
 --amount 1000000ustrd \
 --commission-max-change-rate "0.05" \
 --commission-max-rate "0.10" \
 --commission-rate "0.05" \
 --min-self-delegation "1" \
 --pubkey=$(strided tendermint show-validator) \
 --moniker 'polkachu.com' \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com" \
 --chain-id STRIDE-1 \
 --from stride_test
