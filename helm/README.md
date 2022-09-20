# MINT

![Version: 0.2.1](https://img.shields.io/badge/Version-0.2.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

A Helm chart for MINT

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| auth | object | `{"client_id":"model_catalog","realm":"production","server":"https://auth.mint.isi.edu/auth/realms/production/protocol/openid-connect/token","ui_client_id":"mint-ui","url":"https://auth.mint.isi.edu/auth/"}` | Authentication configuration |
| auth.client_id | string | `"model_catalog"` | Client ID |
| auth.realm | string | `"production"` | Realm |
| auth.server | string | `"https://auth.mint.isi.edu/auth/realms/production/protocol/openid-connect/token"` | Keylocka URL token |
| auth.ui_client_id | string | `"mint-ui"` | Client ID |
| auth.url | string | `"https://auth.mint.isi.edu/auth/"` | Keycloak URL |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| components.cromo | object | `{"enabled":true,"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/cromo","tag":"latest"}}` | Cromo configuration |
| components.data_catalog | object | `{"enabled":true,"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/data-catalog","tag":"15f10f5717870ecf1f9e5fb0f193c5ecbf8c2af3"}}` | Data Catalog configuration |
| components.data_catalog_db.enabled | bool | `true` |  |
| components.data_catalog_db.image.pullPolicy | string | `"IfNotPresent"` |  |
| components.data_catalog_db.image.repository | string | `"mintproject/data-catalog-db"` |  |
| components.data_catalog_db.image.tag | string | `"15f10f5717870ecf1f9e5fb0f193c5ecbf8c2af3"` |  |
| components.hasura | object | `{"enabled":true,"environment":{"enable_console":true,"enable_dev_mode":false,"unauthorized_role":"anonymous"},"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/graphql-engine","tag":"597064529d763ec8df612d239dd54c307de97e57"}}` | GraphQL hasura engine |
| components.hasura_db | object | `{"enabled":true,"image":{"pullPolicy":"IfNotPresent","repository":"postgis/postgis","tag":"10-2.5-alpine"}}` | GraphQL Postgres Database |
| components.model_catalog_api | object | `{"enabled":true,"environment":{"context_dir":"contexts/","graph_base":"http://endpoint.mint.isi.edu/modelCatalog-1.8.0/data/","prefix":"https://w3id.org/okn/i/mint/","queries_dir":"queries/"},"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/model-catalog-api","tag":"latest"}}` | Model Catalog configuration |
| components.model_catalog_endpoint | object | `{"enabled":true,"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/model-catalog-endpoint","tag":"91dabbb1c1f7b2b838e8d8e75a4091e5ec40d4a1"}}` | Model Catalog RDF store configuration |
| components.ui | object | `{"enabled":true,"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/mint-ui-lit","tag":"547b3504e98856f52b3a03e862195384a305b87b"}}` | User Interface configuration |
| fullnameOverride | string | `""` |  |
| google.maps | object | `{"key":"CHANGEME"}` | Google Maps API key |
| google.maps.key | string | `"CHANGEME"` | Google Maps API key |
| hostname | string | `"mint.local"` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations."cert-manager.io/cluster-issuer" | string | `"letsencrypt-prod"` |  |
| ingress.annotations."kubernetes.io/ingress.class" | string | `"public"` |  |
| ingress.annotations."nginx.ingress.kubernetes.io/enable-cors" | string | `"true"` |  |
| ingress.annotations."nginx.ingress.kubernetes.io/proxy-body-size" | string | `"8m"` |  |
| ingress.enabled | bool | `true` |  |
| ingress.tls.enabled | bool | `false` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| resources | object | `{}` |  |
| secrets.database.data_catalog | object | `{"database":"datacatalog","password":"CHANGEME","username":"datacatalog"}` | Data Catalog database credentials |
| secrets.database.hasura | object | `{"database":"hasura","password":"CHANGEME","username":"hasura"}` | GraphQL database credentials |
| secrets.database.model_catalog_endpoint | object | `{"password":"CHANGEME","username":"admin"}` | Model Catalog database credentials |
| secrets.hasura | object | `{"admin_secret":"CHANGEME","jwt_secret":"CHANGE"}` | GraphQL admin credentials |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| shared_storage.access_modes | string | `"ReadWriteMany"` |  |
| shared_storage.backend | string | `"hostpath"` |  |
| shared_storage.hostpath.root_path | string | `"/var/mint"` |  |
| shared_storage.shared_volume_mount_path | string | `"/var/mint"` |  |
| shared_storage.volume_size | int | `200` |  |
| tolerations | list | `[]` |  |
| welcome_message | string | `"Welcome to MINT"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
