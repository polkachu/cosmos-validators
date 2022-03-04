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
| Osmosis        | 27660      | 27656 | 27657 | 27658 | 27060 | 27317      | 27080       | 27090       | 27091           |                 |
| Akash          | 28660      | 28656 | 28657 | 28658 | 28060 | 28317      | 28080       | 28090       | 28091           |                 |
| Chihuahua      | 29660      | 29656 | 29657 | 29658 | 29060 | 29317      | 29080       | 29090       | 29091           |                 |
| Bitcanna       | 30660      | 30656 | 30657 | 30658 | 30060 | 30317      | 30080       | 30090       | 30091           |                 |
| Comdex         | 31660      | 31656 | 31657 | 31658 | 31060 | 31317      | 31080       | 31090       | 31091           | 31300           |
| Sifchain       | 32660      | 32656 | 32657 | 32658 | 32060 | 32327      | 32080       | 32090       | 32091           |                 |

### Osmosis Relayer

| Network           | Prometheus | P2P   | RPC   | ABCI  | Pprof | API server | Rosetta API | gRPC server | gRPC-web server |
| ----------------- | ---------- | ----- | ----- | ----- | ----- | ---------- | ----------- | ----------- | --------------- |
| Osmosis (default) | 26660      | 26656 | 26657 | 26658 | 6060  | 1317       | 8080        | 9090        | 9091            |
| Akash             | 28660      | 28656 | 28657 | 28658 | 28060 | 28317      | 28080       | 28090       | 28091           |
| Chihuahua         | 29660      | 29656 | 29657 | 29658 | 29060 | 29317      | 29080       | 29090       | 29091           |
| Bitcanna          | 30660      | 30656 | 30657 | 30658 | 30060 | 30317      | 30080       | 30090       | 30091           |
| Comdex            | 31660      | 31656 | 31657 | 31658 | 31060 | 31317      | 31080       | 31090       | 31091           |
| Konstellation     | 33660      | 33656 | 33657 | 33658 | 33060 | 33317      | 33080       | 33090       | 33091           |
