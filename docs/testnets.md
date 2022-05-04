## Polkachu's Testnet Setup

We run all testnets on one machine with high CPU, memory and storage. The default ports for each testnet node will conflict. Change the following:

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

| Network     | Custom Port |
| ----------- | ----------- |
| BitCanna    | 56          |
| Comdex      | 39          |
| Defund      | 45          |
| Celestia    | 33          |
| Evmos       | 37          |
| Kichain     | 41          |
| Juno        | default     |
| Quicksilver | 27          |
| Deweb       | 28          |

Make sure the firewalls are open for prometheus port and p2p port

Make sure prometheus is true.
