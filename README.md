# Substrate-based Validator Node Ansible Setup

This repo is to set up a variety of Substrate-based validator nodes. Currently, this script supports:

1. Sora (mainnet)
2. Polkadex (mainnet)
3. Battery Station (testnet for Zeitgeist)

## TL/DR

You run one playbook and set up a node. For example:

```bash
ansible-playbook -i inventory polkadex_full_setup.yml -e "target=polkadex1"
```

But before you rush with this easy setup, you probably want to read on so you understand the structure of this Ansible program and all the features it offers.

## Some Preparations

First of all, make sure that you have a production inventory file with your confidential server info. You will start by copying the sample inventory file (included in the repo). The sample file gives you a good idea on how to define the inventory.

```bash
cp inventory.sample inventory
```

Needless to say, you need to update the dummy values in the inventory file. For each node:

1. Server IP: Your server public IP
2. validator_name: This is the node name that will show up on telemetry monitoring board. For us, we use something like `polkachu-sora-01` and `polkachu-polkadex-01` to keep it unique and organized.
3. log_name: This is for your internal central monitoring server. We just use something like `sora1` and `polkadex1` to keep it simple.
4. telemetry_url: Most likely you will use `wss://telemetry.polkadot.io/submit/`
5. chain_path (optional): You can set an alternative path to store chain data. To be honest, we do not really use it unless we believe that the storage is so large that we need to mount a dedicate drive.

You will also need to update:

1. ansible_user: The sample file assumes `ansible`, but you might have another username. Make sure that the user has `sudo` privilege.
2. ansible_port: The sample file assumes `22`. But if you are like me, you will have a different ssh port other than `22` to avoid port sniffing.
3. ansible_ssh_private_key_file: The sample file assumes `~/.ssh/id_rsa`, but you might have a different key location.
4. log_monitor: Enter your monitor server IP. It is most likely a private IP address if you use a firewall around your private virtual cloud (VPC).

It is beyond the scope of this guide to help you create a sudo user, alternate ssh port, create a private key, install Ansible on your machine, etc. You can do a quick online search and find the answers. In my experience, Digital Ocean have some quality guides on these topics. Stack Overflow can help you trouble-shoot if you are stuck.

## Basic Cluster Structure

We have a rather opinionated node cluster structure. The basic structure is:

1. Name each sora node as `sora1`, `sora2`, etc. Group all Sora nodes into `sora` group.
2. Name each polkadex node as `polkadex1`, `polkadex2`, etc. Group all Polkadex nodes into `polkadex` group.
3. So or and so forth for all other nodes.
4. Group all nodes into a `validators` group.

The structure allows you to target `vars` to each node, or each cluster cluster, or the whole cluster.

Make sure that you are familiar with the files in the `group_vars` folder. They follow this clustered structure closely. The files in this folder often need to be changed to stay up to date with the latest releases.

## Playbook Summary

The key Ansible playbook is `xxx_full_setup.yml`. It will set up a fresh validator from scratch. We also offer separate playbook called `xxx_update_version.yml`. It will update the node version and restart the service.

A generic example for running a playbook is as follows:

```bash
ansible-playbook -i inventory xxx_full_setup.yml -e "target=VALIDATOR_TARGET"
```

Specifically, if you want to set up a fresh Polkadex validator with the target name of `polkadex1`, you run:

```bash
ansible-playbook -i inventory polkadex_full_setup.yml -e "target=polkadex1"
```

## Playbook Dictionary

| Playbook                       | Description                            |
| ------------------------------ | -------------------------------------- |
| `polkadex_full_setup.yml`      | Set up a fresh polkadex validator node |
| `polkadex_update_version.yml ` | Update polkadex validator version      |
| `sora_full_setup.yml`          | Set up a fresh sora validator node     |
| `sora_update_version.yml `     | Update sora validator version          |
| `battery_full_setup.yml`       | Set up a fresh battery validator node  |
| `battery_update_version.yml `  | Update battery validator version       |

## Security and Server Monitoring

We have a rather opinionated security and server monitoring process. The full setup script:

1. Configures firewall and expose/deny ports
2. Installs node_exporter
3. Installs promtail (for log monitoring) that points to an internal log monitoring server

If you do not agree with these, you need to revise the scripts yourself to make it fit with your security and server monitoring process. If you have none of it, you can just run the `xxx_update_version.yml` playbook.

## Nominate Our Validators

- Polkadex: `esqo5YJ4BUPiG2mJrZLLov9hxBtvaUD5M7Bo5ZgkQxLr9X3sb`
- Sora: `cnTkhETZSzY7nZSUgCx1QmYGWWsJ9NKGSPn5CWr92RmXEnbW3`
- Polkadot: `15ym3MDSG4WPABNoEtx2rAzBB1EYWJDWbWYpNg1BwuWRAQcY`
- Kusama: `CsKvJ4fdesaRALc5swo5iknFDpop7YUwKPJHdmUvBsUcMGb`
