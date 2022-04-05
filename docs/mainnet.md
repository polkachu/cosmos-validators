## Polkachu's Mainnet Setup

| Network       | Active? | Rewards Compounding | Snapshot Service | Snapshot Server/Time | Tenderduty | RPC | State Sync | Backup Server | Restake |
| ------------- | ------- | ------------------- | ---------------- | -------------------- | ---------- | --- | ---------- | ------------- | ------- |
| Chihuahua     | Yes     | Self                | Yes              | Minio1: 0:00         | Yes        | Yes | Yes        | Yes           | Yes     |
| Juno          | Yes     | Manual              | Yes              | Minio2: 0:00         | Yes        | Yes | Yes        | Yes           | Yes (x) |
| Akash         | Yes     | Self                | Yes              | Minio1: 0:30         | Yes        | Yes | NOOOOOO!   | Yes           | Yes     |
| Kava          | Yes     | Self                | Yes              | Minio2: 0:30         | Yes        | Yes | Yes        | Yes           | Yes     |
| Sifchain      | Yes     | Self                | Yes              | Minio1: 1:00         | Yes        | Yes | Yes        | Yes           | Yes     |
| Osmosis       | No      | Other               | Yes (main node)  | Minio2: 1:00         | No need    | Yes | Yes        | NOOOOOO!      |         |
| Bitcanna      | Yes     | Self                | Yes              | Minio1: 1:30         | Yes        | Yes | Yes        | Yes           | Yes     |
| Evmos         | Yes     |                     |                  |                      |            |     |            |               | Yes     |
| Comdex        | Yes     | Self                | Yes              | Minio1: 2:00         | Yes        | Yes | Yes        | Yes           | Yes     |
| Umee          | No      | Other               | Yes              | Minio2: 2:00         | Yes        | Yes | Yes        | Yes           |         |
| KiChain       | Yes     | Self                | Yes              | Minio1: 2:30         | Yes        | Yes | Yes        | Yes           | Yes     |
| Stargaze      | Yes     | Self                | Yes              | Minio2: 2:30         | Yes        | Yes | Yes        | Yes           | Yes (x) |
| Cerberus      | Yes     | Self                | Yes              | Minio1: 3:00         | Yes        | Yes | Yes        | Yes           | Yes (x) |
| Certik        | Yes     | Self                | Yes              | Minio2: 3:00         | Yes        | Yes | Yes        | Yes           |         |
| Konstellation | Yes     | Self                | Yes              | Minio1: 3:30         | Yes        | Yes | Yes        | Yes           | Yes     |
| Sommelier     | Yes     | No inflation        | Yes              | Minio2: 3:30         | Yes        | Yes | Yes        | Yes           | Yes     |
| Gravity       | Yes     | Self                | Yes              | Minio1: 4:00         | Yes        | Yes | Yes        | Yes           | Yes (x) |
| Injective     | Yes     |                     | Yes              | Minio2: 4:00         | Yes        | Yes | Yes        | Yes           |         |
| Cosmos        |         |                     | Yes              | Minio1: 4:30         |            | Yes | Yes        | Yes           |         |
| Agoric        |         |                     | Yes              | Minio2: 4:30         |            |     |            |               |         |
| Nomic         | Yes     | Manual              |                  |                      |            |     |            |               |         |

Snapshot service is available at https://polkachu.com/tendermint_snapshots

State-Sync service is available at https://polkachu.com/state_sync

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
