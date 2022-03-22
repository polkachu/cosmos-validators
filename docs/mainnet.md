## Polkachu's Mainnet Setup

| Network       | Active? | Rewards Compounding | Snapshot Service | Snapshot Server/Time | Tenderduty | RPC | API | Backup Server |
| ------------- | ------- | ------------------- | ---------------- | -------------------- | ---------- | --- | --- | ------------- |
| Chihuahua     | Yes     | Self                | Yes              | Minio1: 0:00         | Yes        | Yes |     | Yes           |
| Juno          | Yes     | Manual              | Yes              | Minio2: 0:00         | Yes        | Yes |     | Yes           |
| Akash         | Yes     | Self                | Yes              | Minio1: 1:00         | Yes        | Yes |     | Yes           |
| Kava          | Yes     | Self                | Yes              | Minio2: 1:00         | Yes        | Yes |     | Yes           |
| Sifchain      | Yes     | Self                | Yes              | Minio1: 2:00         | Yes        | Yes |     | Yes           |
| Osmosis       | No      | Other               | Yes (main node)  | Minio2: 2:00         | No need    | Yes |     |               |
| Bitcanna      | Yes     | Self                | Yes              | Minio1: 3:00         | Yes        | Yes |     | Yes           |
| Evmos         | Yes     |                     |                  | Minio2: 3:00 ??      |            |     |     |               |
| Comdex        | Yes     | Self                | Yes              | Minio1: 4:00         | Yes        | Yes |     | Yes           |
| Umee          | No      | Other               | Yes              | Minio2: 4:00         | No need    | Yes |     | Yes           |
| KiChain       | Yes     | Self                | Yes              | Minio1: 5:00         | Yes        | Yes |     | Yes           |
| Stargaze      | No      | Other               | Yes (main node)  | Minio2: 5:00         | No need    | Yes |     |               |
| Cerberus      | Yes     | Self                | Yes              | Minio1: 6:00         | Yes        | Yes |     | Yes           |
| Certik        | No      | Self                | Yes              | Minio2: 6:00         | Not yet    |     |     | Yes           |
| Konstellation | Yes     | Manual              | Yes              | Minio1: 7:00         | Yes        | Yes |     | Yes           |
| Nomic         | Yes     | Manual              |                  |                      |            |     |     |               |

Snapshot service is available at https://polkachu.com/tendermint_snapshots
