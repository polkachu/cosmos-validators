# Cosmos-based Node Ansible Setup Plus Several Supporting Playbooks

## Design Philosophy

1. Extendable to most Tendermint-based chains
1. Support both mainnet and testnet
1. Stable playbooks and roles; Customisable variables
1. Support essential functions (snapshot, state-sync, public RPC/API endpoints and Cosmos Exporter) through seperate playbooks

## TL/DR

You run one playbook and set up a node.

```bash
ansible-playbook main.yml -e "target=juno_main"
```

## Node deployment (Validator, Backup and Relayer)

For every network where we run a validator on mainnet, we run 3 nodes (Validator, Backup and Relayer). The details of our 3-node infrastructure are documented [here](https://polkachu.com/blogs/holy-trinity-a-system-approach-to-tendermint-based-chain-validation).

Take a look at the `inventory.sample` file. You will see an example `juno` group with 3 different hosts: `juno_main`, `juno_backup`, and `juno_relayer`. Each host will have the following variables:

1. `ansible_host`: Required. The IP address of the server.
1. `type`: Required. It can be `main`, `backup` and `realyer` (also `test` if you are adventurous). Each is opinionated in its configuration settings.
1. `prepare`: Optional. If unset, it is default to true. If `false`, it will skip setups of firewall, go, cosmovisor, node exporter, promtail, etc. The reason for the `false` option is because we run many backup/relayer nodes on the same server with setup done already.

Besides the above host variables, you will also specify the following `all` variables in the inventory file:

1. `ansible_user`: The sample file assumes `ubuntu`, but feel free to use other user name. This user need sudo privilege.
1. `ansible_port`: The sample file assumes `22`. But if you are like me, you will have a different ssh port other than `22` to avoid port sniffing.
1. `ansible_ssh_private_key_file`: The sample file assumes `~/.ssh/id_rsa`, but you might have a different key location.
1. `var_file`: It tells the program where to look for the variable file. This is useless for the mainnet, because the var file will automatically be inferred by the network name. However, it is essentially for testnets.
1. `user_dir`: The user's home directory. In the sample inventory file this is a computed variable based on the ansible_user. It assumes that it is not a root user and its home directory is `/home/{{ansible_user}}`.
1. `path`: This is to make sure that the ansible_user can access the `go` executable.
1. `node_exporter`: Default is `true`. Change it to `false` if you do not want to install node_exporter
1. `promtail`: Default is `true`. Change it to `false` if you do not want to install promtail
1. `log_monitor`: Enter your monitor server IP if you install promtail.
1. `node_name`: This is your node name for the config.toml file.
1. `log_name`: This is the server name for the promtail service.

One you understand the setup, please first copy it to your own inventory file so you can customize it to suit your needs:

```bash
cp inventory.sample inventory
```

When you are ready install a node, you run:

```bash
ansible-playbook main.yml -e "target=HOST_NAME"
```

## Playbooks

Playbooks are:

| Playbook                        | Description                                                                         |
| ------------------------------- | ----------------------------------------------------------------------------------- |
| `main.yml`                      | The main playbook to set up a node                                                  |
| `prepare.yml `                  | Prepare the server with node_exporter, promtail, go, cosmovisor, and firewall rules |
| `support_cosmos_exporter.yml `  | Set up Cosmos Exporter configuration (assuming Cosmos Exporter already installed)   |
| `support_public_endpoints.yml ` | Set up Nginx reverse proxy for public PRC/ API                                      |
| `support_snapshot.yml `         | Install snapshot script and a cron job                                              |
| `support_state_sync.yml `       | Install state-sync script                                                           |
| `system_update.yml `            | Update a server and restart if needed                                               |
| `relayer_juno.yml `             | Set up Polkachu's Hermes config for Juno Hub                                        |
| `relayer_osmosis.yml `          | Set up Polkachu's Hermes config for Osmosis Hub                                     |

# Pay attention

Some anomaly in the injective app file. Clean up the end in the app toml file

Some anomaly in the axelar config or app file. Forgot which one it is

Some anomaly in fetch becasue statesync is not supported

Kill polkadex 4, 5

This repo is to set up the Cosmos-based node. It currently support:

- Akash
- BitCanna
- Chihuahua
- Comdex
- Cerberus
- Evmos
- Juno
- Kava
- KiChain
- Osmosis
- Sifchain
- Terra
- Umee
