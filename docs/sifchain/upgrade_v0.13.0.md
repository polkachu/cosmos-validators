# Sifchain v0.13.0 Upgrade

The Upgrade is scheduled for block `6485500`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/6485500)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.13.0
make install
```

# check the version

```bash
# should be 0.13.0
sifnoded version
# Should be commit cff2ed4cfdd55f84d296b5e46d7b63dfa55768e3
sifnoded version --long
```

# Make new directory and copy binary

```bash
mkdir -p $DAEMON_HOME/cosmovisor/upgrades/0.13.0/bin
cp $HOME/go/bin/sifnoded $DAEMON_HOME/cosmovisor/upgrades/0.13.0/bin
```

# check the version again

```bash
# should be 0.13.0
$DAEMON_HOME/cosmovisor/upgrades/0.13.0/bin/sifnoded version
```
