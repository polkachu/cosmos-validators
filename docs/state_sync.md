## State Sync (using Stargaze as example)

```bash
INTERVAL=1500
NODE='https://stargaze.c29r3.xyz:443/rpc'

LATEST_HEIGHT=$(curl -s $NODE/block | jq -r .result.block.header.height);
BLOCK_HEIGHT=$(($LATEST_HEIGHT-$INTERVAL))
TRUST_HASH=$(curl -s "$NODE/block?height=$BLOCK_HEIGHT" | jq -r .result.block_id.hash)

echo "TRUST HEIGHT: $BLOCK_HEIGHT"
echo "TRUST HASH: $TRUST_HASH"

export STARSD_LOG_LEVEL="info"
export STARSD_STATESYNC_ENABLE=true
export STARSD_STATESYNC_RPC_SERVERS="$NODE,$NODE"
export STARSD_STATESYNC_TRUST_HEIGHT=$BLOCK_HEIGHT
export STARSD_STATESYNC_TRUST_HASH=$TRUST_HASH

starsd start

git clone https://github.com/tendermint/tendermint
cd tendermint
git checkout remotes/origin/callum/app-version
go install ./...
tendermint set-app-version 1 --home ~/.starsd

starsd start
```
