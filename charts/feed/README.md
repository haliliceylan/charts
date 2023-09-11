# feed

![Version: 0.1.3](https://img.shields.io/badge/Version-0.1.3-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.0.0](https://img.shields.io/badge/AppVersion-2.0.0-informational?style=flat-square)

A Helm chart for deploying Chronicle Feeds on Kubernetes

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| WesleyCharlesBlake |  | <https://github.com/WesleyCharlesBlake> |
| chronicleprotocol |  | <https://github.com/chronicleprotocol> |

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://chronicleprotocol.github.io/charts/ | ghost | 0.1.6 |
| https://chronicleprotocol.github.io/charts/ | musig | 0.0.6 |
| https://chronicleprotocol.github.io/charts/ | tor-proxy | 0.0.8 |

## Values

| Key                                           | Type   | Default                                                                                                        | Description                   |
|-----------------------------------------------|--------|----------------------------------------------------------------------------------------------------------------|-------------------------------|
| extraObjects                                  | list   | `[]`                                                                                                           | Extra K8s manifests to deploy |
| ghost.chainId                                 | string | `nil`                                                                                                          |                               |
| ghost.enabled                                 | bool   | `true`                                                                                                         |                               |
| ghost.env.normal.CFG_WEBAPI_ENABLE            | int    | `1`                                                                                                            |                               |
| ghost.env.normal.CFG_WEBAPI_LISTEN_ADDR       | string | `""`                                                                                                           |                               |
| ghost.env.normal.CFG_WEBAPI_SOCKS5_PROXY_ADDR | string | `"tor-proxy:9050"`                                                                                             |                               |
| ghost.ethChainId                              | string | `nil`                                                                                                          |                               |
| ghost.ethConfig                               | object | `{}`                                                                                                           |                               |
| ghost.ethRpcUrl                               | string | `nil`                                                                                                          |                               |
| ghost.fullnameOverride                        | string | `"ghost"`                                                                                                      |                               |
| ghost.image.tag                               | string | `"0.15.2"`                                                                                                     |                               |
| ghost.logFormat                               | string | `nil`                                                                                                          |                               |
| ghost.logLevel                                | string | `nil`                                                                                                          |                               |
| ghost.rpcUrl                                  | string | `nil`                                                                                                          |                               |
| ghost.service.ports.libp2p.port               | int    | `8000`                                                                                                         |                               |
| ghost.service.ports.libp2p.protocol           | string | `"TCP"`                                                                                                        |                               |
| ghost.service.type                            | string | `"ClusterIP"`                                                                                                  |                               |
| musig.enabled                                 | bool   | `true`                                                                                                         |                               |
| musig.env.normal.CFG_WEBAPI_ENABLE            | int    | `1`                                                                                                            |                               |
| musig.env.normal.CFG_WEBAPI_LISTEN_ADDR       | string | `":8080"`                                                                                                      |                               |
| musig.env.normal.CFG_WEBAPI_SOCKS5_PROXY_ADDR | string | `"tor-proxy:9050"`                                                                                             |                               |
| musig.ethChainId                              | int    | `1`                                                                                                            |                               |
| musig.ethConfig                               | object | `{}`                                                                                                           |                               |
| musig.ethRpcUrl                               | string | `nil`                                                                                                          |                               |
| musig.fullnameOverride                        | string | `"musig"`                                                                                                      |                               |
| musig.image.tag                               | string | `"0.4.1"`                                                                                                      |                               |
| musig.imagePullSecrets                        | list   | `[]`                                                                                                           |                               |
| musig.logFormat                               | string | `nil`                                                                                                          |                               |
| musig.logLevel                                | string | `nil`                                                                                                          |                               |
| musig.service.ports.libp2p.port               | int    | `8001`                                                                                                         |                               |
| musig.service.ports.libp2p.protocol           | string | `"TCP"`                                                                                                        |                               |
| musig.service.ports.webapi.port               | int    | `8080`                                                                                                         |                               |
| musig.service.ports.webapi.protocol           | string | `"TCP"`                                                                                                        |                               |
| musig.service.type                            | string | `"ClusterIP"`                                                                                                  |                               |
| tor-proxy.enabled                             | bool   | `true`                                                                                                         |                               |
| tor-proxy.env.normal.TOR_EXTRA_ARGS           | string | `"SocksPort 0.0.0.0:9050\nHiddenServiceDir /var/lib/tor/hidden_services\nHiddenServicePort 8888 musig:8080\n"` |                               |
| tor-proxy.fullnameOverride                    | string | `"tor-proxy"`                                                                                                  |                               |
| tor-proxy.service.ports.socks.port            | int    | `9050`                                                                                                         |                               |
| tor-proxy.service.ports.socks.protocol        | string | `"TCP"`                                                                                                        |                               |
| tor-proxy.service.type                        | string | `"ClusterIP"`                                                                                                  |                               |
| tor-proxy.torConfig                           | object | `{}`                                                                                                           |                               |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)