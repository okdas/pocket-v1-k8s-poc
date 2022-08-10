# Pocket V1 PoC in K8s

## Validators

Currently we only have one actor on the network - the validator.

Included k8s manifests deploys 4 validators (as included in genesis).

## Client

Separate container is deployed to run the client. Just shell onto it and execute `client` binary. It allows to turn on and off the validators, send some messages to the network, etc.

## Postgres

Each validator requires a postgres DB, so we have one schema per validator within the same database.