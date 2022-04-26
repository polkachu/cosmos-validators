# Akash v0.16.1 Upgrade

The Upgrade is scheduled for block `5629650`. A countdown clock is [here](https://www.mintscan.io/akash/blocks/5629650)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd akash
git fetch --all
git checkout v0.16.1
make install
```

# check the version

```bash
# should be 0.16.1
akash version
# Should be commit 1ab8ee6ebd1321d98fb899c8661316cf182a4d4d
akash version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.akash/cosmovisor/upgrades/akash_v0.15.0_cosmos_v0.44.x/bin
cp $(which akash) $HOME/.akash/cosmovisor/upgrades/akash_v0.15.0_cosmos_v0.44.x/bin
```

# check the version again

```bash
# should be 0.16.1
$HOME/.akash/cosmovisor/upgrades/akash_v0.15.0_cosmos_v0.44.x/bin/akash version
```
