# Polkachu Mainnet Setup Notes

## Eth bridging

| Network   | Validator key | Cosmos Orchestrator Key | Ethereum Orchestrator Key                  |
| --------- | ------------- | ----------------------- | ------------------------------------------ |
| Gravity   | Default       | Default Orchestrator    | 0x99E43230eCec926a7FFc2E4CD22153494D5a84a3 |
| Sommelier | Default       | Default Orchestrator    | 0x99E43230eCec926a7FFc2E4CD22153494D5a84a3 |
| Umee      | Default       | Umee Orchestrator / Bot | 0x99E43230eCec926a7FFc2E4CD22153494D5a84a3 |
| Injective | Default       | Injective Orchestrator  | 0xB497abA1E4Ce24B4ADc2E16Ded30387042B881B7 |

## Other exception

| Network       | Validator key | Reason                            |
| ------------- | ------------- | --------------------------------- |
| Konstellation | Test key      | Mistake when setting up validator |

## Polkachu's Relayer Setup

We run all relayers on one machine with high CPU, memory and storage. The default ports for each testnet node will conflict. Change the following:

`config.toml`

- P2P: 26656 (default)
- RPC: 26657 (default)
- ABCI: 26658 (default)
- Pprof: 6060 (default)
- Prometheus: 26660 (default)

`app.toml`

- API server: 1317 (default)
- Rosetta API server: 8080 (default)
- gRPC server: 9090 (default)
- gRPC-web server: 9091 (default)

Make sure the firewalls are open for prometheus port and p2p port. Make sure prometheus is set to true.

Tips for setting up a new chain on relayers:

1. Make sure that ports from different relayer hubs are open to each other.
1. When manually installing binary, make sure to refer to some group_vars doc for github repo, genesis file, seeds, peers and minimum-gas-price
1. For relayers, make sure that pruning is 40000/0/prime number, and the indexer is kv.
1. Make sure that RPC port (657 port) is open to the other relayers. We manage it by opening to all (0.0.0.0) in the config file and let firewall to manage the whitelist IPs (e.g., other relayers)
1. Make sure to open P2P port and Prometheus port to all
1. Add the new service as dependency for hermes service
1. Make sure to set up cosmos exporter for the new service and open the cosmos exporter port
1. Sometimes the relayer node also serves as state_sync node, PRC and API. This is not the best practice. However, this allows us to utilize underused server resources and make us manage fewer servers

Our app.toml settings related to state-sync is as follows:

```bash
pruning-keep-every = 2000
snapshot-interval = 2000
snapshot-keep-recent = 5
```

Our app.toml settings related to api server is as follows (does not work on Kava):

```bash
[api]
enabled = true
swagger = true
```
