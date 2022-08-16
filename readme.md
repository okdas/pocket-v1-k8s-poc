# Pocket V1 PoC in K8s



# How to bring the stack online.

1. Must provision postgres database prior to starting the validators. Example for k3s (`HelmChart` object) [included](postgres.yml). `kubectl apply -f postgres.yml`
2. Once postgres is up and running, the rest of the validators can be provisioned: `kubectl apply -f .`

## Validators

Currently we only have one actor on the network - validator.

Included k8s manifests deploys 4 validators (as configured in genesis).

## Client

Separate container is deployed to run the client. Just shell onto it and execute `client` binary. It allows to turn on and off the validators, send some messages to the network, etc.

## Postgres

Each validator requires a postgres DB, so we have one schema per validator within the same database.