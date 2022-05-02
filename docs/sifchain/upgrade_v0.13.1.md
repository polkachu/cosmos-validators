# Sifchain v0.13.1 Upgrade

The Upgrade is scheduled for block `6678500`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/6678500)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.13.1
make install
```

# check the version

```bash
# should be 0.13.1
sifnoded version
# Should be commit 70cc6d46e6458a1d681b858470a65c50ba351bac
sifnoded version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.sifnoded/cosmovisor/upgrades/0.13.1/bin
cp $HOME/go/bin/sifnoded $HOME/.sifnoded/cosmovisor/upgrades/0.13.1/bin
```

# check the version again

```bash
# should be 0.13.1
$HOME/.sifnoded/cosmovisor/upgrades/0.13.1/bin/sifnoded version
```
