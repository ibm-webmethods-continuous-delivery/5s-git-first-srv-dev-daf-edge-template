# 5s-git-first-srv-dev-daf-edge-template
A template to start service development for DAF Edge servers

## Notes

When registering a new ERT "replica", the IWHI wizard proposes the following command

```sh
METERING_TOKEN='...'
CLOUD_REGISTRATION_TOKEN='...'
CLOUD_EDGE_NAME='TestERT'
CLOUD_EDGE_ALIAS='EdgeRuntime_${CLOUD_EDGE_NAME}'
CLOUD_INT_TENANT_URL='https://...int.ipaas.automation.ibm.com'

docker run -p 5555:5555  -d \
-e SAG_IS_CLOUD_REGISTER_URL="${CLOUD_INT_TENANT_URL}" \
-e SAG_IS_EDGE_CLOUD_ALIAS="${CLOUD_EDGE_ALIAS}" \
-e SAG_IS_CLOUD_REGISTER_TOKEN="${CLOUD_REGISTRATION_TOKEN}" \
-e METERING_TOKEN="${METERING_TOKEN}" \
--name="${CLOUD_EDGE_NAME}" \
iwhicr.azurecr.io/webmethods-edge-runtime:12.0.2
```

The token should be manually generated for repeated pairing. Use the OAuth admin page for this purpose.

Procure the necessary values and use the .env files to pass them to the docker compose projects.
