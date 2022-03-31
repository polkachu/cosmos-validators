## Polkachu's Mainnet Setup

| Network       | Active? | Rewards Compounding | Snapshot Service | Snapshot Server/Time | Tenderduty | RPC | State Sync | Backup Server |
| ------------- | ------- | ------------------- | ---------------- | -------------------- | ---------- | --- | ---------- | ------------- |
| Chihuahua     | Yes     | Self                | Yes              | Minio1: 0:00         | Yes        | Yes | Yes        | Yes           |
| Juno          | Yes     | Manual              | Yes              | Minio2: 0:00         | Yes        | Yes |            | Yes           |
| Akash         | Yes     | Self                | Yes              | Minio1: 1:00         | Yes        | Yes |            | Yes           |
| Kava          | Yes     | Self                | Yes              | Minio2: 1:00         | Yes        | Yes | Yes        | Yes           |
| Sifchain      | Yes     | Self                | Yes              | Minio1: 2:00         | Yes        | Yes | Yes        | Yes           |
| Osmosis       | No      | Other               | Yes (main node)  | Minio2: 2:00         | No need    | Yes | Yes        |               |
| Bitcanna      | Yes     | Self                | Yes              | Minio1: 3:00         | Yes        | Yes | Yes        | Yes           |
| Evmos         | Yes     |                     |                  | Minio2: 3:00 ??      |            |     |            |               |
| Comdex        | Yes     | Self                | Yes              | Minio1: 4:00         | Yes        | Yes | Yes        | Yes           |
| Umee          | No      | Other               | Yes              | Minio2: 4:00         | No need    | Yes | Yes        | Yes           |
| KiChain       | Yes     | Self                | Yes              | Minio1: 5:00         | Yes        | Yes | Yes        | Yes           |
| Stargaze      | No      | Other               | Yes (main node)  | Minio2: 5:00         | No need    | Yes |            |               |
| Cerberus      | Yes     | Self                | Yes              | Minio1: 6:00         | Yes        | Yes | Yes        | Yes           |
| Certik        | No      | Self                | Yes              | Minio2: 6:00         | Yes        | Yes | Yes        | Yes           |
| Konstellation | Yes     | Manual              | Yes              | Minio1: 7:00         | Yes        | Yes | Yes        | Yes           |
| Sommelier     | Yes     | No inflation        | Yes              | Minio2: 7:00         | Yes        | Yes | Yes        | Yes           |
| Gravity       |         |                     | Yes              | Minio1: 8:00         |            | Yes | Yes        | Yes           |
| Injective     |         |                     | Yes              | Minio2: 8:00         |            | Yes | Yes        | Yes           |
| Cosmos        |         |                     | Yes              | Minio1: 9:00         |            | Yes | Yes        | Yes           |
| Nomic         | Yes     | Manual              |                  |                      |            |     |            |               |

Snapshot service is available at https://polkachu.com/tendermint_snapshots

State-Sync service is available at https://polkachu.com/state_sync

## Eth bridging

| Network   | Validator key | Cosmos Orchestrator Key | Ethereum Orchestrator Key |
| --------- | ------------- | ----------------------- | ------------------------- |
| Gravity   | Default       | Sommelier Orchestrator  | Default                   |
| Sommelier | Default       | Sommelier Orchestrator  | Default                   |
| Umee      | Default       | Umee Orchestrator / Bot | Default                   |

## Other exception

| Network       | Validator key | Reason                            |
| ------------- | ------------- | --------------------------------- |
| Konstellation | Test key      | Mistake when setting up validator |
