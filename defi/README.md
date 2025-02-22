# defillama-server

## Setup
```bash
aws configure
```

## Development
```bash
npm run build # Build with webpack & check for type errors
npm test # Run tests
npm run format # Format code
```

### Local dev server
```bash
npm run serve
```

## Deploy
Just push your changes to the `master` branch.

## Filling data
```
# fetch latest adapters (important to run this before any refilling commands)
npm run updateAdapters

# fill old historical data
npm run fillOld aave # start refilling aave from now and 1 at a time
npm run fillOld aave 1648098107 # start refilling aave from 1648098107 going backwards 1 at a time
npm run fillOld aave now 4 # start refilling aave from now going backwards 4 at a time

# fill latest data point
npm run fillLast aave
```

If you run into the error `Error: Cannot find module '[...]'` then run:
```
npm run prebuild
```

Run general scripts:
```
export AWS_REGION='eu-central-1' && export tableName='prod-table' && npx ts-node src/<script>
```