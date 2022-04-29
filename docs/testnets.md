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

| Network       | Custom Port |
| ------------- | ----------- |
| Juno          | default     |
| Kava          | 46          |
| BitCanna      | 56          |
| Konstellation | 32          |
| Celestia      | 33          |
| Omniflix      | 34          |
| Comdex        | 39          |
| Kichain       | 41          |
| Defund        | 45          |

Make sure the firewalls are open for prometheus port and p2p port

Make sure prometheus is true.
