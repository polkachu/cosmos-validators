# Injective 10005 Upgrade using Cosmovisor

The Upgrade is scheduled for block `9614200`. A countdown clock is [here](https://www.mintscan.io/injective/blocks/9614200).

Get the new version

```bash
wget https://github.com/InjectiveLabs/injective-chain-releases/releases/download/v1.5.0-1649280277/linux-amd64.zip
unzip linux-amd64.zip
mv injectived $HOME/go/bin
```

Remove unused files

```bash
rm injective-exchange
rm peggo
rm linux-amd64.zip
```

Check the version - should be 568ce23

```bash
injectived version
Version dev (568ce23)
Compiled at 20220406-2125 using Go go1.18 (amd64)
```

If you are using cosmovisor, you then need to create folder and copy this new binary

```bash
mkdir -p $DAEMON_HOME/cosmovisor/upgrades/v1.5/bin
cp /home/<your-user>/go/bin/injectived $DAEMON_HOME/cosmovisor/upgrades/v1.5/bin
```

Find out what version you are about to run - should be 568ce23

```bash
$DAEMON_HOME/cosmovisor/upgrades/v1.5/bin/injectived version
```
