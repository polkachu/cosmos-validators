# Cosmos-based Node Ansible Setup

This repo is to set up the Cosmos-based node. It currently support:

- Juno (mainnet and testnet)
- Sifchain (betanet and testnet)
- Evmos (testnet)

## Summary

You run one playbook and set up a node. For example:

```bash
ansible-playbook -i inventory juno_full_setup.yml -e "target=juno_testnet"
```

But before you rush with this easy setup, you probably want to read on so you understand the structure of this Ansible program and all the features it offers.

## Some Preparations

First, make sure that you have a production inventory file with your confidential server info. You will start by copying the sample inventory file (included in the repo). The sample file gives you a good idea on how to define the inventory.

```bash
cp inventory.sample inventory
```

Needless to say, you need to update the dummy values in the inventory file. For each node, you need to update the server IP. While you are free to keep the default, you might also want to update:

1. ansible_user: The sample file assumes `ubuntu`.
2. ansible_port: The sample file assumes `22`. But if you are like me, you will have a different ssh port other than `22` to avoid port sniffing.
3. ansible_ssh_private_key_file: The sample file assumes `~/.ssh/id_rsa`, but you might have a different key location.
4. log_monitor: Enter your monitor server IP. It is most likely a private IP address if you use a firewall around your private virtual cloud (VPC).

It is beyond the scope of this guide to help you create a sudo user, alternate ssh port, create a private key, install Ansible on your machine, etc. You can do a quick online search and find the answers. In my experience, Digital Ocean have some quality guides on these topics. Stack Overflow can help you trouble-shoot if you are stuck.

## Basic Cluster Structure

The basic cluster structure is:

1. Name each juno node as `juno_testnet`, `juno_mainnet`, etc. Group all Juno nodes into `juno` group.
2. Name each juno node as `sifchain_testnet`, `sifchain_mainnet`, etc. Group all Sifchain nodes into `sifchain` group.
3. ...

The structure allows you to target `vars` to each node, or a group cluster, or the whole cluster. Make sure that you are familiar with the files in the `group_vars` folder. They follow this clustered structure closely.

## Main Playbook

The key Ansible playbook is `xxxxx_full_setup.yml` files. It will set up a fresh node from scratch. For example:

```bash
ansible-playbook -i inventory sifchain_full_setup.yml -e "target=sifchain_betanet"
```

## Some Useful Commands

block height

```bash
watch -n 60 -d "curl -s http://localhost:26657/status | jq -r .result.sync_info.latest_block_height"
```

Connected Peers

```bash
curl -s localhost:26657/net_info | jq -r '.result.peers[] | .node_info.moniker, .node_info.id, .node_info.listen_addr, .remote_ip'
```

Check logs and cosmovisor status

```bash
journalctl -u cosmovisor.service -f
journalctl -u cosmovisor.service -f | grep "committed"
systemctl status cosmovisor
```

Sifchain: create validator

```bash
sifnoded tx staking create-validator \
 --amount 1000000000000000000000rowan \
 --commission-max-change-rate "0.01" \
 --commission-rate "0.02" \
 --commission-max-rate "0.1" \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --pubkey=$(sifnoded tendermint show-validator) \
 --moniker 'Polkachu' \
 --chain-id sifchain-1 \
 --gas-adjustment="1.5" \
 --gas="200000" \
 --fees 100000000000000000rowan \
 --from polkachu
```

Sifchain: Delegate

```bash
sifnoded tx staking delegate sifvaloper1gp957czryfgyvxwn3tfnyy2f0t9g2p4pfj2j90 420000000000000000000rowan \
 --chain-id sifchain-1 \
 --from=polkachu \
 --gas-adjustment="1.5" \
 --gas="200000" \
 --fees 100000000000000000rowan
```

Juno: create validator

```bash
junod tx staking create-validator \
 --amount 6000000ujunox \
 --commission-max-change-rate "0.1" \
 --commission-max-rate "0.20" \
 --commission-rate "0.1" \
 --min-self-delegation "1" \
 --details "This is my validator" \
 --pubkey=$(junod tendermint show-validator) \
 --moniker '[Polkachu] 1% fee' \
 --chain-id uni \
 --gas-prices 0.025ujunox \
 --from polkachu
```
