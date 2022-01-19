# Kava-9 Migration

[Official Migration Guide](https://github.com/Kava-Labs/kava/blob/master/migrate/v0_16/migrate.md)

[Peers and Seed](https://docs.google.com/spreadsheets/d/1j-e1HTkskNRS6mlhxLLQa0loB-ShcVUjz8WVVZxvPaY/edit#gid=0)

[Todd's Genesis File](https://share.blockpane.com/kava-9-genesis.json.gz)

Always verify the genesis file has the right hash if you download genesis file from others

```
jq -S -c -M '' genesis.json | shasum -a 256
5c688df5ae6cba9c9e5a9bab045eb367dd54ce9b7f5fab78cf3e636cf2e2b793  -
```
