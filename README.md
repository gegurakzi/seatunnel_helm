# Helm chart for Apache SeaTunel on Kubernetes

## [About Apache SeaTunnel](https://seatunnel.apache.org/docs/2.3.5/about)

### Configurations

| Parameter                                | Default                     | Description                                                                                                                                     |
|------------------------------------------|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| `replicaCount`                           | `3`                         |                                                                                                                                                 |
| `image.repository`                       | `seatunnel-dependency`      |                                                                                                                                                 |
| `image.pullPolicy`                       | `IfNotPresent`              |                                                                                                                                                 |
| `image.tag`                              | `latest`                    |                                                                                                                                                 |
| `imagePullSecrets`                       | `[]`                        |                                                                                                                                                 |
| `nameOverride`                           | `''`                        |                                                                                                                                                 |
| `fullnameOverride`                       | `''`                        |                                                                                                                                                 |
| `podAnnotations`                         | `{}`                        |                                                                                                                                                 |
| `podLabels`                              | `{}`                        |                                                                                                                                                 |
| `podSecurityContext`                     | `{}`                        |                                                                                                                                                 |
| `securityContext`                        | `{}`                        |                                                                                                                                                 |
| `service.type`                           | `LoadBalancer`              |                                                                                                                                                 |
| `resources.limits.cpu`                   | `1`                         |                                                                                                                                                 |
| `resources.limits.memory`                | `4G`                        |                                                                                                                                                 |
| `resources.requests.cpu`                 | `1`                         |                                                                                                                                                 |
| `resources.requests.memory`              | `2G`                        |                                                                                                                                                 |
| `volumes`                                | in values.yaml              |                                                                                                                                                 |
| `volumeMounts`                           | in values.yaml              |                                                                                                                                                 |
| `reloader.enabled`                       | `false`                     |                                                                                                                                                 |
| `reloader.image.repository`              | `ghcr.io/stakater/reloader` |                                                                                                                                                 |
| `reloader.image.pullPolicy`              | `IfNotPresent`              |                                                                                                                                                 | 
| `reloader.image.tag`                     | `v1.0.82`                   |                                                                                                                                                 |
| `reloader.labels`                        | in values.yaml              |                                                                                                                                                 |
| `reloader.serviceAccount`                | in values.yaml              |                                                                                                                                                 |
| `configmaps.hazelcastClient`             | in values.yaml              | format of Configmap `hazelcast-client`. template automatically assigns the elements of `cluster-members` with `replicaCount`                    |
| `configmaps.hazelcast`                   | in values.yaml              | format of Configmap `hazelcast`. template automatically assigns the elements of `member-list` with `replicaCount`                               |
| `configmaps.seatunnelmap`                | in values.yaml              | format of Configmap `seatunnelmap`.                                                                                                             |
| `configmaps.seatunnelConfig.fileName`    | `seatunnel.streaming.conf`  | example SeaTunnel job configuration file. you should also change values in `volumes` and `volumeMounts` if you want to change its path or name. |

### Installing the Chart
To install the chart execute:
```
helm install seatunnel path/to/charts/seatunnel
```
