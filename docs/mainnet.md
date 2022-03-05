## Polkachu's Mainnet Setup

| Network   | Active? | Pruning | Rewards Compounding                    | Snapshot Service | Backup / Snapshot Server | PRC Server |
| --------- | ------- | ------- | -------------------------------------- | ---------------- | ------------------------ | ---------- |
| Chihuahua | Yes     | Default | Automated and enter Pool 605 daily     | Yes              | Minio1: 0:00             |            |
| Juno      | Yes     | Default | Automated and delegate to self daily   | Yes              | Minio2: 0:00             |            |
| Akash     | Yes     | Default | Automated and delegate to others daily | Yes              | Minio1: 1:00             |            |
| Kava      | Yes     | Default | Automated and delegate to self daily   | Yes              | Minio2: 1:00             |            |
| Sifchain  | Yes     | Default | Automated and delegate to self daily   | Yes              | Minio1: 2:00             |            |
| Osmosis   | No      | Default | Automated and delegate to others daily | Yes (main node)  | Minio2: 2:00             |            |
| Bitcanna  | Yes     | Default | Automated and delegate to self daily   | Yes              | Minio1: 3:00             |            |
| Evmos     | Yes     | Default | Not yet                                | Yes              | Minio2: 3:00             |            |
| Comdex    | No      | Default | Automated and delegate to others daily | Yes              | Minio1: 4:00             |            |
| Umee      | No      | Default | N/A                                    | Yes (main node)  | Minio2: 4:00             |            |
| KiChain   | Yes     | Default | Automated and delegate to self daily   | Yes              | Minio1: 5:00             |            |
| Stargaze  | No      | Default | Automated and delegate to others daily | Yes (main node)  | Minio2: 5:00             |            |

Snapshot service is available at https://polkachu.com/tendermint_snapshots
