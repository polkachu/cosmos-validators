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

| Network       | P2P     | RPC     | ABCI    | Pprof   | Prometheus | API server | Rosetta API | gRPC server | gRPC-web server |
| ------------- | ------- | ------- | ------- | ------- | ---------- | ---------- | ----------- | ----------- | --------------- |
| Juno          | default | default | default | default | default    | default    | default     | default     | default         |
| Osmosis       | 36656   | 36657   | 36658   | 36060   | 36660      | 31317      | 38080       | 39090       | 39091           |
| Kava          | 46656   | 46657   | 46658   | 46060   | 46660      | 41317      | 48080       | 49090       | 49091           |
| BitCanna      | 56656   | 56657   | 56658   | 56060   | 56660      | 51317      | 58080       | 59090       | 59091           |
| Deweb         | 31656   | 31657   | 31658   | 31060   | 31660      | 31317      | 31080       | 31090       | 31091           |
| Konstellation | 32656   | 32657   | 32658   | 32060   | 32660      | 32317      | NA          | 32090       | 32091           |
| Celestia      | 33656   | 33657   | 33658   | 33060   | 33660      | 33317      | 33080       | 33090       | 33091           |
| Omniflix      | 34656   | 34657   | 34658   | 34060   | 34660      | 34317      | 34080       | 34090       | 34091           |

Make sure the firewalls are open for prometheus port and p2p port

Make sure prometheus is true.
