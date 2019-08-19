# Helm Chart for FADI

[![CircleCI](https://circleci.com/gh/cetic/helm-fadi.svg?style=svg)](https://circleci.com/gh/cetic/helm-fadi/tree/master) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) ![version](https://img.shields.io/github/tag/cetic/helm-fadi.svg?label=release)

## Introduction

This [Helm](https://github.com/kubernetes/helm) chart installs [fadi](https://github.com/cetic/fadi) in a Kubernetes cluster.
You can optionally enable/disable components of fadi.

## Prerequisites

- Kubernetes cluster 1.10+
- Helm 2.8.0+
- PV provisioner support in the underlying infrastructure.

## Chart Details

See the [fadi](https://github.com/cetic/fadi) repository for documentation and defaults.

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
| `spark.enabled`                                                             | Enable Spark                                                                                                       | `true`                          |
| `superset.enabled`                                                          | Enable Superset                                                                                                    | `true`                          |
| `postgresql.enabled`                                                        | Enable PostgreSQL                                                                                                  | `true`                          |
| `minio.enabled`                                                             | Enable Minio                                                                                                       | `true`                          |
| `grafana.enabled`                                                           | Enable Grafana                                                                                                     | `true`                          |
| `jupyterhub.enabled`                                                        | JupyterHub Security Token. See the [preparation of the configuration file](https://z2jh.jupyter.org/en/latest/setup-jupyterhub.html#prepare-configuration-file). | `af83775ec3bfaf0507ce596df51d491e7ed54450adc454038fa7405495465f19`|
| `jupyterhub.proxy.secretToken`                                              | Enable JupyterHub                                                                                                  | `true`                          |
| `nifi.enabled`                                                              | Enable Nifi                                                                                                        | `true`                          |
| `pgadmin.enabled`                                                           | Enable PgAdmin                                                                                                     | `true`                          |
| `openldap.enabled`                                                          | Enable openldap                                                                                                    | `true`                          |
| `phpldapadmin.enabled`                                                      | Enable phpLDAPadmin                                                                                                | `true`                          |

## Contributing

Feel free to contribute by making a [pull request](https://github.com/cetic/helm-fadi/pull/new/master).

Please read the official [Contribution Guide](https://github.com/helm/charts/blob/master/CONTRIBUTING.md) from Helm for more information on how you can contribute to this Chart.

