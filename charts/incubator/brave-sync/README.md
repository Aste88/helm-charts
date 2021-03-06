# brave-sync

![Version: 0.0.2](https://img.shields.io/badge/Version-0.0.2-informational?style=flat-square) ![AppVersion: v0.1.19](https://img.shields.io/badge/AppVersion-v0.1.19-informational?style=flat-square)

brave-sync helm package

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/Aste88/helm-charts/issues/new/choose)**

## Source Code

* <https://github.com/brave/go-sync>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://aste88.github.io/helm-charts/ | dynamo-db | 0.0.2 |
| https://charts.bitnami.com/bitnami | redis | 16.6.0 |
| https://library-charts.k8s-at-home.com | common | 4.4.2 |

## TL;DR

```console
helm repo add Aste88 https://aste88.github.io/helm-charts/
helm repo update
helm install brave-sync Aste88/brave-sync
```

## Installing the Chart

To install the chart with the release name `brave-sync`

```console
helm install brave-sync Aste88/brave-sync
```

## Uninstalling the Chart

To uninstall the `brave-sync` deployment

```console
helm uninstall brave-sync
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install brave-sync \
  --set env.TZ="America/New York" \
    Aste88/brave-sync
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install brave-sync Aste88/brave-sync -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| dynamo-db.data.enabled | bool | `false` |  |
| dynamo-db.data.mountPath | string | `"/data"` |  |
| dynamo-db.enabled | bool | `false` |  |
| dynamo-db.persistence | string | `nil` |  |
| env | object | See below | environment variables. See more environment variables in the [gitea documentation](https://gitea.org/docs). |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/aste88/brave/sync"` | image repository |
| image.tag | string | `nil` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| redis | object | See values.yaml | Enable and configure redis subchart under this key.    For more options see [redis chart documentation](https://github.com/bitnami/charts/tree/master/bitnami/redis) |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 0.0.2

#### Added

N/A

#### Changed

N/A

#### Fixed

* fix Chart.yaml fields values's and ENVs

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/aste88-helm-charts/brave-sync?modal=changelog)

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/Aste88/helm-charts/issues/new/choose)

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/k8s-at-home/helm-docs/releases/v0.1.1)
