# Gravity v1.5.2

The Upgrade is scheduled for block `1888600`. A countdown clock is [here](https://www.mintscan.io/gravity/blocks/1888600)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
wget https://github.com/Gravity-Bridge/Gravity-Bridge/releases/download/v1.5.2/gravity-linux-amd64
mv gravity-linux-amd64 $HOME/go/bin/gravity
chmod +x $HOME/go/bin/gravity
```

# check the version

```bash
# should be v1.5.2
gravity version
# Should be commit e6fba8cfebfbc01659f71eaad70421203f3cfc46
gravity version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.gravity/cosmovisor/upgrades/mercury2.0/bin
cp $HOME/go/bin/gravity $HOME/.gravity/cosmovisor/upgrades/mercury2.0/bin
```

# check the version again

```bash
# should be v1.5.2
$HOME/.gravity/cosmovisor/upgrades/mercury2.0/bin/gravity version
```
