# Sifchain v0.12.1 Upgrade

The Upgrade is scheduled for block `6270250`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/6270250)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.12.1
make install
```

# check the version and checksum

```bash
# should be 0.12.1
sifnoded version
# Should be commit 269cfadf6a4c08879247c2b8373323ae7239a425
sifnoded version --long
# Should be e8a98733a69c62b6782c3b87ddaaf0be215666e520d3143c7e69347456d04c8b
sha256sum sifnoded
```

# Make new directory and copy binary

```bash
mkdir -p $DAEMON_HOME/cosmovisor/upgrades/0.12.1/bin
cp $HOME/go/bin/sifnoded $DAEMON_HOME/cosmovisor/upgrades/0.12.1/bin
```

# check the version again

```bash
# should be 0.12.1
$DAEMON_HOME/cosmovisor/upgrades/0.12.1/bin/sifnoded version
```
