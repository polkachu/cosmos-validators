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

| Network                         | P2P     | RPC     | ABCI    | Pprof   | Prometheus | API server | Rosetta API | gRPC server | gRPC-web server |
| ------------------------------- | ------- | ------- | ------- | ------- | ---------- | ---------- | ----------- | ----------- | --------------- |
| Juno                            | default | default | default | default | default    | default    | default     | default     | default         |
| Osmosis                         | 36656   | 36657   | 36658   | 36060   | 36660      | 31317      | 38080       | 39090       | 39091           |
| Kava                            | 46656   | 46657   | 46658   | 46060   | 46660      | 41317      | 48080       | 49090       | 49091           |
| BitCanna                        | 56656   | 56657   | 56658   | 56060   | 56660      | 51317      | 58080       | 59090       | 59091           |
| Deweb                           | 31656   | 31657   | 31658   | 31060   | 31660      | 31317      | 31080       | 31090       | 31091           |
| Konstellation                   | 32656   | 32657   | 32658   | 32060   | 32660      | 32317      | NA          | 32090       | 32091           |
| Celestia                        | 33656   | 33657   | 33658   | 33060   | 33660      | 33317      | 33080       | 33090       | 33091           |
| Omniflix                        | 34656   | 34657   | 34658   | 34060   | 34660      | 34317      | 34080       | 34090       | 34091           |
| Craft                           | 35656   | 35657   | 35658   | 35060   | 35660      | 35317      | 35080       | 35090       | 35091           |
| Evmos                           | 37656   | 37657   | 37658   | 37060   | 37660      | 37317      | 37080       | 37090       | 37091           |
| Cosmos Horizon                  | 38656   | 38657   | 38658   | 38060   | 38660      | 38317      | 38080       | 38090       | 38091           |
| Comdex                          | 39656   | 39657   | 39658   | 39060   | 39660      | 39317      | 39080       | 39099       | 39098           |
| Cerberus                        | 40656   | 40657   | 40658   | 40060   | 40660      | 40317      | 40080       | 40099       | 40098           |
| Kichain                         | 41656   | 41657   | 41658   | 41060   | 41660      | 41317      | 41080       | 41099       | 41098           |
| Vacant (ports are open already) | 42656   | 42657   | 42658   | 42060   | 42660      | 42317      | 42080       | 42099       | 42098           |

Make sure the firewalls are open for prometheus port and p2p port

Make sure prometheus is true.
