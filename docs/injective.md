## Injective

create validator

```bash
injectived tx staking create-validator \
    --moniker='polkachu-injective-mainnet' \
    --amount=1000000000000000000inj \
    --gas-prices=500000000inj \
    --pubkey=$(injectived tendermint show-validator) \
    --website "https://polkachu.com" \
    --moniker='polkachu.com'
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --chain-id='injective-1' \
    --keyring-backend=file \
    --yes \
    --node=tcp://localhost:26657 \
    --commission-max-change-rate=0.01 \
    --commission-max-rate=0.1 \
    --commission-rate=0 \
    --min-self-delegation=1 \
    --from=polkachu
```

Edit Validator

```bash
injectived tx staking edit-validator \
  --moniker="polkachu.com" \
  --gas-prices=500000000inj \
  --chain-id='injective-1' \
  --from=polkachu
```

Register Orchestrator and Ethereum Address

```bash
injectived tx peggy set-orchestrator-address inj125fkz3mq6qxxpkmphdl3ep92t0d3y969raza70 inj125fkz3mq6qxxpkmphdl3ep92t0d3y969raza70 0xB497abA1E4Ce24B4ADc2E16Ded30387042B881B7 \
    --chain-id=injective-1 \
    --keyring-backend=file \
    --yes  \
    --node=tcp://localhost:26657  \
    --gas-prices=500000000inj \
    --from polkachu
```

Send Injective

```bash
injectived tx bank send polkachu inj1cef7jxy9xg3c5dka9spdv0hpjv0nu3hsy5238p 1000000000000000000inj --chain-id=injective-1 --keyring-backend=file --yes --node=tcp://localhost:26657 --gas-prices=500000000inj
```
