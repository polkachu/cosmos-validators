## Terra

### Testnet

Create validator

```bash
terrad tx staking create-validator \
    --amount=5000000uluna \
    --pubkey=$(terrad tendermint show-validator) \
    --moniker 'polkachu.com' \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --chain-id=bombay-12 \
    --from=polkachu \
    --commission-max-change-rate "0.01" \
    --commission-rate "0.02" \
    --commission-max-rate "0.1" \
    --min-self-delegation "1" \
    --fees=3000uluna \
    --from=polkachu
```

Set oracle

```bash
terrad tx oracle set-feeder terra13v9q6pek6cwu4js989d22wl8sdm48j4r9cnrg7 --from=polkachu --chain-id=bombay-12 --fees=3000uluna
```

```bash
npm start vote -- \
   --source http://localhost:8532/latest \
   --lcd https://lcd.terra.dev \
   --chain-id columbus-5 \
   --validator terravaloper168epm0dvd6v9kpxjz2x800sad0mq4sm9herwzz \
   --password "<password>"
```
