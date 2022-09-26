# MINT

![Version: 0.2.2](https://img.shields.io/badge/Version-0.2.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

A Helm chart for MINT

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| auth | object | `{"client_id":"client","realm":"realm","ui_client_id":"client","url":"https://auth.example.com/"}` | Authentication configuration |
| auth.client_id | string | `"client"` | Client ID |
| auth.realm | string | `"realm"` | Realm |
| auth.ui_client_id | string | `"client"` | Client ID |
| auth.url | string | `"https://auth.example.com/"` | Keycloak URL |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| components.cromo | object | `{"enabled":true,"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/cromo","tag":"latest"},"ingress":{"annotations":{},"className":"","enabled":true,"hosts":[{"host":"cromo.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}}` | Cromo configuration |
| components.cromo.image.pullPolicy | string | `"IfNotPresent"` | cromo image pull policy |
| components.cromo.image.repository | string | `"mintproject/cromo"` | cromo image repository |
| components.cromo.image.tag | string | `"latest"` | cromo image tag |
| components.cromo.ingress | object | `{"annotations":{},"className":"","enabled":true,"hosts":[{"host":"cromo.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | cromo ingress configuration |
| components.cromo.ingress.annotations | object | `{}` | cromo ingress annotations |
| components.cromo.ingress.className | string | `""` | cromo ingress class name |
| components.cromo.ingress.enabled | bool | `true` | enable the cromo ingress |
| components.cromo.ingress.hosts | list | `[{"host":"cromo.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}]` | cromo ingress hosts |
| components.cromo.ingress.tls | list | `[]` | cromo ingress tls configuration |
| components.data_catalog.enabled | bool | `true` | enable the data catalog component |
| components.data_catalog.image.pullPolicy | string | `"IfNotPresent"` | data catalog image pull policy |
| components.data_catalog.image.repository | string | `"mintproject/data-catalog"` | data catalog image repository |
| components.data_catalog.image.tag | string | `"15f10f5717870ecf1f9e5fb0f193c5ecbf8c2af3"` | data catalog image tag |
| components.data_catalog.ingress | object | `{"annotations":{},"className":"","enabled":true,"hosts":[{"host":"datacatalog.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | data catalog ingress configuration |
| components.data_catalog.ingress.annotations | object | `{}` | data catalog ingress annotations |
| components.data_catalog.ingress.className | string | `""` | data catalog ingress class name |
| components.data_catalog.ingress.enabled | bool | `true` | enable the data catalog ingress |
| components.data_catalog.ingress.hosts | list | `[{"host":"datacatalog.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}]` | data catalog ingress hosts |
| components.data_catalog.ingress.tls | list | `[]` | data catalog ingress tls configuration |
| components.data_catalog_db | object | `{"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/data-catalog-db","tag":"15f10f5717870ecf1f9e5fb0f193c5ecbf8c2af3"}}` | data database component |
| components.data_catalog_db.image.pullPolicy | string | `"IfNotPresent"` | data catalog database image pull policy |
| components.data_catalog_db.image.repository | string | `"mintproject/data-catalog-db"` | data catalog database image repository |
| components.data_catalog_db.image.tag | string | `"15f10f5717870ecf1f9e5fb0f193c5ecbf8c2af3"` | data catalog database image tag |
| components.hasura | object | `{"enabled":true,"environment":{"enable_console":true,"enable_dev_mode":false,"unauthorized_role":"anonymous"},"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/graphql-engine","tag":"597064529d763ec8df612d239dd54c307de97e57"},"ingress":{"annotations":{},"className":null,"enabled":true,"hosts":[{"host":"graphql.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}}` | GraphQL hasura engine |
| components.hasura.enabled | bool | `true` | enable the hasura component |
| components.hasura.environment | object | `{"enable_console":true,"enable_dev_mode":false,"unauthorized_role":"anonymous"}` | hasura environment variables |
| components.hasura.environment.enable_console | bool | `true` | enable the hasura console |
| components.hasura.environment.enable_dev_mode | bool | `false` | enable the hasura dev mode |
| components.hasura.environment.unauthorized_role | string | `"anonymous"` | unauthenticated role |
| components.hasura.image | object | `{"pullPolicy":"IfNotPresent","repository":"mintproject/graphql-engine","tag":"597064529d763ec8df612d239dd54c307de97e57"}` | hasura image repository |
| components.hasura.image.pullPolicy | string | `"IfNotPresent"` | hasura image pull policy |
| components.hasura.image.repository | string | `"mintproject/graphql-engine"` | hasura image repository |
| components.hasura.image.tag | string | `"597064529d763ec8df612d239dd54c307de97e57"` | hasura image tag |
| components.hasura.ingress | object | `{"annotations":{},"className":null,"enabled":true,"hosts":[{"host":"graphql.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | hasura ingress configuration |
| components.hasura.ingress.annotations | object | `{}` | hasura ingress annotations |
| components.hasura.ingress.className | string | `nil` | hasura ingress class name |
| components.hasura.ingress.enabled | bool | `true` | enable the hasura ingress |
| components.hasura.ingress.hosts | list | `[{"host":"graphql.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}]` | hasura ingress hosts |
| components.hasura.ingress.tls | list | `[]` | hasura ingress tls configuration |
| components.hasura_db | object | `{"image":{"pullPolicy":"IfNotPresent","repository":"postgis/postgis","tag":"10-2.5-alpine"}}` | GraphQL Postgres Database |
| components.hasura_db.image | object | `{"pullPolicy":"IfNotPresent","repository":"postgis/postgis","tag":"10-2.5-alpine"}` | hasura database image repository |
| components.hasura_db.image.pullPolicy | string | `"IfNotPresent"` | hasura database image pull policy |
| components.hasura_db.image.repository | string | `"postgis/postgis"` | hasura database image repository |
| components.hasura_db.image.tag | string | `"10-2.5-alpine"` | hasura database image tag |
| components.model_catalog_api | object | `{"enabled":true,"environment":{"context_dir":"contexts/","graph_base":"http://endpoint.mint.isi.edu/modelCatalog-1.8.0/data/","prefix":"https://w3id.org/okn/i/mint/","queries_dir":"queries/"},"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/model-catalog-api","tag":"latest"},"ingress":{"annotations":{},"className":"","enabled":true,"hosts":[{"host":"api.models.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}}` | Model Catalog configuration |
| components.model_catalog_api.enabled | bool | `true` | enable the model catalog api component |
| components.model_catalog_api.environment | object | `{"context_dir":"contexts/","graph_base":"http://endpoint.mint.isi.edu/modelCatalog-1.8.0/data/","prefix":"https://w3id.org/okn/i/mint/","queries_dir":"queries/"}` | model catalog api environment variables  |
| components.model_catalog_api.environment.context_dir | string | `"contexts/"` | where are the contexts stored |
| components.model_catalog_api.environment.graph_base | string | `"http://endpoint.mint.isi.edu/modelCatalog-1.8.0/data/"` | the graph prefix used by the RDF store |
| components.model_catalog_api.environment.prefix | string | `"https://w3id.org/okn/i/mint/"` | uri of the RDF resource |
| components.model_catalog_api.environment.queries_dir | string | `"queries/"` | where are the queries templates stored |
| components.model_catalog_api.image | object | `{"pullPolicy":"IfNotPresent","repository":"mintproject/model-catalog-api","tag":"latest"}` | model catalog api image details  |
| components.model_catalog_api.image.pullPolicy | string | `"IfNotPresent"` | model catalog api image pull policy |
| components.model_catalog_api.image.repository | string | `"mintproject/model-catalog-api"` | model catalog api image repository |
| components.model_catalog_api.image.tag | string | `"latest"` | model catalog api image tag |
| components.model_catalog_api.ingress | object | `{"annotations":{},"className":"","enabled":true,"hosts":[{"host":"api.models.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | model catalog api ingress configuration |
| components.model_catalog_api.ingress.annotations | object | `{}` | model catalog api ingress annotations |
| components.model_catalog_api.ingress.className | string | `""` | model catalog api ingress class name |
| components.model_catalog_api.ingress.enabled | bool | `true` | enable the model catalog api ingress |
| components.model_catalog_api.ingress.hosts | list | `[{"host":"api.models.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}]` | model catalog api ingress hosts |
| components.model_catalog_api.ingress.tls | list | `[]` | model catalog api ingress tls configuration |
| components.model_catalog_endpoint | object | `{"enabled":true,"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/model-catalog-endpoint","tag":"91dabbb1c1f7b2b838e8d8e75a4091e5ec40d4a1"},"ingress":{"annotations":{},"className":"","enabled":true,"hosts":[{"host":"endpoint.models.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}}` | Model Catalog RDF store configuration |
| components.model_catalog_endpoint.enabled | bool | `true` | enable the model catalog endpoint component |
| components.model_catalog_endpoint.image | object | `{"pullPolicy":"IfNotPresent","repository":"mintproject/model-catalog-endpoint","tag":"91dabbb1c1f7b2b838e8d8e75a4091e5ec40d4a1"}` | model catalog endpoint image repository |
| components.model_catalog_endpoint.image.pullPolicy | string | `"IfNotPresent"` | model catalog endpoint image pull policy |
| components.model_catalog_endpoint.image.repository | string | `"mintproject/model-catalog-endpoint"` | model catalog endpoint image repository |
| components.model_catalog_endpoint.image.tag | string | `"91dabbb1c1f7b2b838e8d8e75a4091e5ec40d4a1"` | model catalog endpoint image tag |
| components.model_catalog_endpoint.ingress | object | `{"annotations":{},"className":"","enabled":true,"hosts":[{"host":"endpoint.models.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | model catalog endpoint ingress configuration |
| components.model_catalog_endpoint.ingress.annotations | object | `{}` | model catalog endpoint ingress annotations |
| components.model_catalog_endpoint.ingress.className | string | `""` | model catalog endpoint ingress class name |
| components.model_catalog_endpoint.ingress.enabled | bool | `true` | enable the model catalog endpoint ingress |
| components.model_catalog_endpoint.ingress.hosts | list | `[{"host":"endpoint.models.mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}]` | model catalog endpoint ingress hosts |
| components.model_catalog_endpoint.ingress.tls | list | `[]` | model catalog endpoint ingress tls configuration |
| components.ui | object | `{"enabled":true,"image":{"pullPolicy":"IfNotPresent","repository":"mintproject/mint-ui-lit","tag":"547b3504e98856f52b3a03e862195384a305b87b"},"ingress":{"annotations":{},"className":"","enabled":true,"hosts":[{"host":"mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}}` | User Interface configuration |
| components.ui.enabled | bool | `true` | enable the ui component |
| components.ui.image | object | `{"pullPolicy":"IfNotPresent","repository":"mintproject/mint-ui-lit","tag":"547b3504e98856f52b3a03e862195384a305b87b"}` | ui image details |
| components.ui.image.pullPolicy | string | `"IfNotPresent"` | ui image pull policy |
| components.ui.image.repository | string | `"mintproject/mint-ui-lit"` | ui image repository |
| components.ui.image.tag | string | `"547b3504e98856f52b3a03e862195384a305b87b"` | ui image tag |
| components.ui.ingress | object | `{"annotations":{},"className":"","enabled":true,"hosts":[{"host":"mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | ui ingress configuration |
| components.ui.ingress.annotations | object | `{}` | ui ingress annotations |
| components.ui.ingress.className | string | `""` | ui ingress class name |
| components.ui.ingress.enabled | bool | `true` | enable the ui ingress |
| components.ui.ingress.hosts | list | `[{"host":"mint.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}]` | ui ingress hosts |
| components.ui.ingress.tls | list | `[]` | ui ingress tls configuration |
| fullnameOverride | string | `""` |  |
| google.maps | object | `{"key":"CHANGEME"}` | Google Maps API key |
| google.maps.key | string | `"CHANGEME"` | Google Maps API key |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| resources | object | `{}` |  |
| secrets.database.data_catalog | object | `{"database":"datacatalog","password":"CHANGEME","username":"datacatalog"}` | Data Catalog database credentials |
| secrets.database.data_catalog.database | string | `"datacatalog"` | Data Catalog database name |
| secrets.database.data_catalog.password | string | `"CHANGEME"` | Data Catalog database password |
| secrets.database.data_catalog.username | string | `"datacatalog"` | Data Catalog database username |
| secrets.database.hasura | object | `{"database":"hasura","password":"CHANGEME","username":"hasura"}` | GraphQL database credentials |
| secrets.database.hasura.database | string | `"hasura"` | GraphQL database name |
| secrets.database.hasura.password | string | `"CHANGEME"` | GraphQL database password |
| secrets.database.hasura.username | string | `"hasura"` | GraphQL database username |
| secrets.database.model_catalog_endpoint | object | `{"password":"CHANGEME","username":"admin"}` | Model Catalog database credentials |
| secrets.database.model_catalog_endpoint.password | string | `"CHANGEME"` | Model Catalog database password |
| secrets.database.model_catalog_endpoint.username | string | `"admin"` | Model Catalog database username |
| secrets.hasura | object | `{"admin_secret":"CHANGEME","jwt_secret":"CHANGE"}` | GraphQL admin credentials |
| secrets.hasura.admin_secret | string | `"CHANGEME"` | HASURA_GRAPHQL_ADMIN_SECRET |
| secrets.hasura.jwt_secret | string | `"CHANGE"` | RS256 JWT public certificate from the OIDC provider |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| shared_storage.access_modes | string | `"ReadWriteMany"` | Shared volume access mode |
| shared_storage.backend | string | `"hostpath"` | Shared volume storage backend |
| shared_storage.hostpath | object | `{"root_path":"/var/mint"}` | Path to the MINT directory inside the underlying storage volume |
| shared_storage.shared_volume_mount_path | string | `"/var/mint"` | Path inside the MINT components where the shared volume will be mounted |
| shared_storage.volume_size | int | `200` | Shared volume size |
| tolerations | list | `[]` |  |
| welcome_message | string | `"Welcome to MINT"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
