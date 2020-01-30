# Helm Chart for FADI

[![CircleCI](https://circleci.com/gh/cetic/helm-fadi.svg?style=svg)](https://circleci.com/gh/cetic/helm-fadi/tree/master) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) ![version](https://img.shields.io/github/tag/cetic/helm-fadi.svg?label=release)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fcetic%2Fhelm-fadi.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fcetic%2Fhelm-fadi?ref=badge_shield)

## Introduction

This [Helm](https://github.com/kubernetes/helm) chart installs [fadi](https://github.com/cetic/fadi) in a Kubernetes cluster.
You can optionally enable/disable components of fadi.

## Prerequisites

- Kubernetes cluster 1.10+
- Helm 2.8.0+
- PV provisioner support in the underlying infrastructure.

## Chart Details

See the [fadi](https://github.com/cetic/fadi) repository for documentation and userguide.

## Installation

### Add Helm repository

```bash
helm repo add cetic https://cetic.github.io/helm-charts
helm repo update
```

### Install the chart

Install the fadi helm chart with a release name `my-release`:

```bash
helm install --name my-release cetic/fadi
```

## Uninstallation

To uninstall/delete the `my-release` deployment:

```bash
helm delete --purge my-release
```

Deletion of the StatefulSet doesn't cascade to deleting associated PVCs. To delete them:

```bash
kubectl delete pvc -l release=my-release,component=data
```

## Configuration

Each requirement is configured with the options provided by that Chart. Please consult the relevant charts for their configuration options.

| Parameter                                                                   | Description                                                                                                        | Default                         |
| --------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------| ------------------------------- |
| **FADI tools**                                                              |
| `spark.enabled`                                                             | Enable [Spark](https://github.com/helm/charts/tree/master/stable/spark)                                            | `true`                          |
| `superset.enabled`                                                          | Enable [Superset](https://github.com/helm/charts/tree/master/stable/superset)                                      | `true`                          |
| `postgresql.enabled`                                                        | Enable [PostgreSQL](https://github.com/cetic/helm-postgresql)                                                      | `true`                          |
| `minio.enabled`                                                             | Enable [Minio](https://github.com/helm/charts/tree/master/stable/minio)                                            | `true`                          |
| `grafana.enabled`                                                           | Enable [Grafana](https://github.com/helm/charts/tree/master/stable/grafana)                                        | `true`                          |
| `jupyterhub.enabled`                                                        | Enable [JupyterHub](https://github.com/jupyterhub/helm-chart)                                                      | `true`                          |
| `nifi.enabled`                                                              | Enable [Nifi](https://github.com/cetic/helm-nifi)                                                                  | `true`                          |                          |
| `openldap.enabled`                                                          | Enable [Openldap](https://github.com/helm/charts/tree/master/stable/openldap)                                      | `true`                          |
| `phpldapadmin.enabled`                                                      | Enable [PhpLDAPadmin](https://github.com/cetic/helm-phpLDAPadmin)                                                  | `true`                          |
| `kafka.enabled`                                                             | Enable [Kafka](https://github.com/helm/charts/tree/master/incubator/kafka)                                         | `false`                         |
| `cassandra.enabled`                                                         | Enable [Cassandra](https://github.com/helm/charts/tree/master/incubator/cassandra)                                 | `false`                         |
| `filebeat.enabled`                                                          | Enable [Filebeat](https://github.com/helm/charts/tree/master/stable/filebeat)                                      | `false`                         |
| `logstash.enabled`                                                          | Enable [Logstash](https://github.com/helm/charts/tree/master/stable/logstash)                                      | `false`                         |
| `elasticsearch.enabled`                                                     | Enable [Elasticsearch](https://github.com/helm/charts/tree/master/stable/elasticsearch)                            | `false`                         |
| `kibana.enabled`                                                            | Enable [Kibana](https://github.com/helm/charts/tree/master/stable/kibana)                                          | `false`                         |
| `nginx-ldapauth-proxy.enabled`                                              | Enable [nginx-ldapauth-proxy](https://github.com/helm/charts/tree/master/stable/nginx-ldapauth-proxy)              | `false`                         |
| `tsaas.enabled`                                                             | Enable [Tsimulus-saas](https://github.com/cetic/helm-tsimulus-saas)                                                | `false`                         |
| `swaggerui.enabled`                                                         | Enable [Swaggerui](https://github.com/cetic/helm-swagger-ui)                                                       | `false`                         |
| `node-red.enabled`                                                          | Enable [Node-red](https://github.com/helm/charts/tree/master/stable/node-red)                                      | `false`                         |
| `adminer.enabled`                                                           | Enable [Adminer](https://github.com/cetic/helm-adminer)                                                            | `true`                         |

## Contributing

Feel free to contribute by making a [pull request](https://github.com/cetic/helm-fadi/pull/new/master).

Please read the official [Contribution Guide](https://github.com/helm/charts/blob/master/CONTRIBUTING.md) from Helm for more information on how you can contribute to this Chart.

## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fcetic%2Fhelm-fadi.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fcetic%2Fhelm-fadi?ref=badge_large)
