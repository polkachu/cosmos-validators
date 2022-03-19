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

Make sure the firewalls are open for prometheus port and p2p port. Make sure prometheus is true.

### Juno Relayer

| Network        | Prometheus | P2P   | RPC   | ABCI  | Pprof | API server | Rosetta API | gRPC server | gRPC-web server | Cosmos Exporter |
| -------------- | ---------- | ----- | ----- | ----- | ----- | ---------- | ----------- | ----------- | --------------- | --------------- |
| Juno (default) | 26660      | 26656 | 26657 | 26658 | 6060  | 1317       | 8080        | 9090        | 9091            | 9300            |
| Sifchain       | 32660      | 32656 | 32657 | 32658 | 32060 | 32317      | 32080       | 32090       | 32091           | 32300           |
| Evmos          | 34660      | 34656 | 34657 | 34658 | 34060 | 34317      | 34080       | 34090       | 34091           | 34300           |
| Kichain        | 35660      | 35656 | 35657 | 35658 | 35060 | 35317      | 35080       | 35090       | 35091           | 35300           |
| Umee           | 36660      | 36656 | 36657 | 36658 | 36060 | 36317      | 36080       | 36090       | 36091           | 36300           |
| Stargaze       | 37660      | 37656 | 37657 | 37658 | 37060 | 37317      | 37080       | 37090       | 37091           | 37300           |
| Cerberus       | 38660      | 38656 | 38657 | 38658 | 38060 | 38317      | 38080       | 38090       | 38091           | 38300           |

### Osmosis Relayer

| Network           | Prometheus | P2P   | RPC   | ABCI  | Pprof | API server | Rosetta API | gRPC server | gRPC-web server | Cosmos Exporter |
| ----------------- | ---------- | ----- | ----- | ----- | ----- | ---------- | ----------- | ----------- | --------------- | --------------- |
| Osmosis (default) | 26660      | 26656 | 26657 | 26658 | 6060  | 1317       | 8080        | 9090        | 9091            | 9300            |
| Akash             | 28660      | 28656 | 28657 | 28658 | 28060 | 28317      | 28080       | 28090       | 28091           | 28300           |
| Chihuahua         | 29660      | 29656 | 29657 | 29658 | 29060 | 29317      | 29080       | 29090       | 29091           | 29300           |
| Bitcanna          | 30660      | 30656 | 30657 | 30658 | 30060 | 30317      | 30080       | 30090       | 30091           | 30300           |
| Comdex            | 31660      | 31656 | 31657 | 31658 | 31060 | 31317      | 31080       | 31090       | 31091           | 31300           |
| Konstellation     | 33660      | 33656 | 33657 | 33658 | 33060 | 33317      | 33080       | 33090       | 33091           | 33300           |

Tips for setting up a new chain on relayers:

1. Make sure that ports from different relayer hubs are open to each other.
1. When manually installing binary, make sure to refer to some group_vars doc for github repo, genesis file, seeds, peers and minimum-gas-price
1. For relayers, make sure that pruning is 40000/0/prime number, and the indexer is kv.
1. Make sure that RPC port is open to the other relayers. We manage it by opening to all (0.0.0.0) in the config file and let firewall to manage the whitelist IPs (e.g., other relayers)
1. Make sure to open P2P port and Prometheus port to all
1. Add the new service as dependency for hermes service
1. Make sure to set up cosmos exporter for the new service and open the cosmos exporter port
1. Sometimes the relayer node also serves as state_sync node, PRC and API. This is not the best practice. However, this allows us to utilize underused server resources and make us manage fewer servers

Our app.toml settings related to state-sync is as follows:

```bash
pruning-keep-every = 1000
snapshot-interval = 1000
snapshot-keep-recent = 5
```

Our app.toml settings related to api server is as follows:

```bash
[api]
enabled = true
swagger = true
```

| Network   | State Sync                                | RPC                                | API                                |
| --------- | ----------------------------------------- | ---------------------------------- | ---------------------------------- |
| Bitcanna  | https://polkachu.com/state_sync/bitcanna  | https://bitcanna-rpc.polkachu.com  | https://bitcanna-api.polkachu.com  |
| Chihuahua | https://polkachu.com/state_sync/chihuahua | https://chihuahua-rpc.polkachu.com | https://chihuahua-api.polkachu.com |
| Osmosis   | https://polkachu.com/state_sync/osmosis   | https://osmosis-rpc.polkachu.com   | https://osmosis-api.polkachu.com   |
| Comdex    | https://polkachu.com/state_sync/comdex    | https://comdex-rpc.polkachu.com    | https://comdex-api.polkachu.com    |
