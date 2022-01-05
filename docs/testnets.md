## Polkachu's Testnet Setup

We run all testnets on one machine with high CPU, memory and storage. The default ports for each testnet node will conflict. Change the following:

`config.toml`

- P2P: 26656 (default)
- RPC: 26657 (default)
- ABCI: 26658 (default)
- Prometheus: 26660 (default)

`app.toml`

- API server: 1317 (default)
- Rosetta API server: 8080 (default)
- gRPC server: 9090 (default)
- gRPC-web server: 9091 (default)

| Network | P2P     | RPC     | ABCI    | Prometheus | API server | Rosetta API | gRPC server | gRPC-web server |
| ------- | ------- | ------- | ------- | ---------- | ---------- | ----------- | ----------- | --------------- |
| Juno    | default | default | default | default    | default    | default     | default     | default         |
| Osmosis | 36656   | 36657   | 36658   | 36660      | 31317      | 38080       | 39090       | 39091           |

Make sure the firewalls are open for prometheus port and p2p port
