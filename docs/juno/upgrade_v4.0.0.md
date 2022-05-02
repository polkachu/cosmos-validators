# Juno v4.0.0 Upgrade

The Upgrade is scheduled for block `2951100`. A countdown clock is [here](https://www.mintscan.io/juno/blocks/2951100)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd juno
git pull
git checkout v4.0.0
make install
```

# check the version

```bash
# should be make install
junod version
# Should be commit 299fe4bdee7a7a8b45cd2776359243fdf3630e5a
junod version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.juno/cosmovisor/upgrades/unity/bin
cp $HOME/go/bin/junod $HOME/.juno/cosmovisor/upgrades/unity/bin
```

# check the version again

```bash
# should be v4.0.0
$HOME/.juno/cosmovisor/upgrades/unity/bin/junod version
```
