## Validator Server Migration Best Practices

When we run a mainnet validator for a network, we always try to run a fully-synced non-validator node as backup. Here we want to share some of my learnings in practicing validator swap with a fully synced node.

### Scenario

We have two nodes: validator Node A and fully-synced non-validator Node B. Both are running under the management of cosmovisor. We have a backup copy of "priv_validator_key.json" from Node A. We want to move the validator role from Node A to Node B.

### Best Practice

1. **Stop Node A**: Stop `cosmovisor` service on Node A. Double check the service status to make sure it is off. On block explorer, you should see the validator missing blocks. In addition, we implement two safeguards against unexpected restart. First, we change `priv_validator_key.json` to `priv_validator_key.json.backup` in the `config` folder. Second, we change `cosmovisor.service` to `cosmovisor.service.backup` in the `systemd` folder.

2. **Change Validator Role to Node B**: Stop Node B's `cosmovisor` service. Replace Node B's `priv_validator_key.json` with the backup copy from A. Restart B's `cosmovisor` service. Make sure it is making blocks on block explorer.

3. **Make Node A the New Non-Validator Node**: Delete `priv_validator_key.json.backup` (created from Step 1) in the `config` folder on Node A. Change `cosmovisor.service.backup` back to `cosmovisor.service` in the `systemd` folder on Node A. Restart Node A's `cosmovisor` service. Because there is no `priv_validator_key.json` on Node A at this moment, the service will create a new copy of priv_validator_key.json. Check logs to make sure that Node A is making blocks.

4. **House Clean**: The specifics only apply to how we set up the cluster. You should adapt according to your setup.
   - Swap the server name with "sudo hostname xxx" on each server (for example, between "juno_mainnet" and "juno_mainnet_backup")
   - Swap the server shortcut in ~/.ssh/config file for each ssh login
   - Swap the log name in the promtail.yml file on each server and restart promtail.
   - Swap the server hosts in the monitoring server deployment script so Prometheus and Grafana get the servers right. Redeploy the monitoring script
   - Update the server names on the server provider (Hetzner, Contabo, AWS, GCP) to avoid confusion
   - Update the inventory file in the cosmos server deployment script. This is not very important since the deployment of both servers are completed. However, it is so to avoid future confusions because both servers will still be running, although in the opposite role of validator vs. non-validator.
