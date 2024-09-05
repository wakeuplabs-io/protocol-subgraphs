# Custom Deploy

## Configuration

The project contains a `config` folder, where each network's configuration is stored. Each configuration file follows this structure:

```json
{
  "network": "bob-testnet", // network key from thegraph
  "PoolAddressesProviderRegistryAddress": "",
  "PoolAddressesProviderRegistryStartBlock": ,
  "AaveOracleAddress": "",
  "AaveOracleStartBlock": ,
  "RewardsControllerAddress": "",
  "RewardsControllerStartBlock": ": 
}
```

- `network`: Network identifier used by The Graph (e.g., "bob-testnet")
- `PoolAddressesProviderRegistryAddress`: Address of the Pool Addresses Provider Registry
- `PoolAddressesProviderRegistryStartBlock`: Block number from which to start indexing
- `AaveOracleAddress`: Address of the Aave Oracle contract
- `AaveOracleStartBlock`: Block number for the Aave Oracle
- `RewardsControllerAddress`: Address of the Rewards Controller. In the deployment folder, it is called `IncentivesV2-Implementation.json`.
- `RewardsControllerStartBlock`: Block number for the Rewards Controller.

Ensure to fill in the necessary addresses and block numbers for each network. The block number should correspond to the block in which the deployment was done to optimize load and avoid losing any events.

## Development

```bash

# copy env and adjust its content with your personal access token and subgraph name

# you can get an access token from https://thegraph.com/explorer/dashboard
cp .env.test .env

# install project dependencies
npm i

# to regenrate types if schema.graphql has changed
npm run subgraph:codegen

# to run a test build of your subgraph
npm run subgraph:build

# now you're able to deploy to thegraph hosted service with one of the deploy commands:
npm run deploy:hosted:bob-testnet-v3

```
