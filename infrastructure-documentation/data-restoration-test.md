# data restoration test

These are notes from the data restoration test conducted on 26h April 2021.

## Test script

1. Make changes in the three significant data stores: Keycloak, Graph and Rocket Chat
2. Shut down environment in a controlled manner
3. Stand it back up via the infrastructure orchestration
4. Check that the changes are still in place.

\(Keycloak data = preferred name, password  
Graph data = profiles  
Rocket chat = Rocket chat\)

## Tech script

### Shut down

1. Set environment to down in infrastructure
2. Run the `./build` script

### Stand up

1. Find the ARN for the latest Identity DB snapshot. Do this by navigating to AWS Services -&gt; RDS -&gt; Snapshots -&gt; Manual. Find the most most recent one for the environment. \(Or alternatively the one which you want to restore\).
2. Paste Snapshot ARN into the configuration for staging
3. Set the environment state to up
4. Run the `./build` script

## Observations

* Stack removal times \(total run 45 mins\):
  * UI - approx 11 mins
  * Graph - approx 7 mins
  * Neo4j - approx 2 mins
  * Chat - approx 4 mins
  * Identity - approx 16 mins
  * Loadbalancer - approx 10 seconds!
* Stack stand up times \(total run time 24 mins\)
  * Loadbalancer - approx 2 mins
  * Identity - approx 10 mins
  * Chat - approx 1.5 mins
  * Neo4j - approx 1.5 mins
  * Graph - approx 1 mins
  * UI - approx 5 mins

