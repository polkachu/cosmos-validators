# Sifchain v0.11.0 Upgrade

The Upgrade is scheduled for block `5870400`. This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.11.0
make install

# check the version - should be 0.11.0
# sifnoded version --long will be commit dfdb014de4fff090c559b628d903555d8ccdc957
sifnoded version

# if you are using cosmovisor, you then need to create folder and copy this new binary
mkdir -p $DAEMON_HOME/cosmovisor/upgrades/0.11.0/bin
cp /home/<your-user>/go/bin/sifnoded $DAEMON_HOME/cosmovisor/upgrades/0.11.0/bin

# find out what version you are about to run - should be 0.11.0
$DAEMON_HOME/cosmovisor/upgrades/0.11.0/bin/sifnoded version
```
