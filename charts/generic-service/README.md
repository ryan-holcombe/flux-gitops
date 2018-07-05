# Helm Chart

## Configuration

|       Parameter           |           Description               |                         Default                          |
|---------------------------|-------------------------------------|----------------------------------------------------------|
| `name`                    | k8s selector key                    | `s3api`                                                  |
| `image.name`              | app name                            | `s3api`                                                  |
| `image.tag`               | Container image tag                 | `latest`                                                 |
| `imagePullPolicy`         | Container pull policy               | `Always`                                                 |
| `imageReplicaCount`       | k8s deployment replicas             | `3`                                                      |
| `imageResources`          | container requested cpu             | `{cpu: "100m", memory: "128Mi"}`                         |
| `imagePullSecrets`        | image pull secret for private repo  |                                                          |
| `livenessProbe.enabled`   | Enable Liveness probe               | `true`                                                   |
| `livenessProbe.path`      | Liveness probe http path            | `/healthz`                                               |
| `readinessProbe.enabled`  | Enable Readiness probe              | `true`                                                   |
| `readinessProbe.path`     | Readiness probe http path           | `/healthz`                                               |
| `service.type`            | k8s service type                    | `ClusterIP`                                              |
| `service.internalPort`    | Container listening port            | `8888`                                                   |
| `service.externalPort`    | k8s service port                    | `80`                                                     |
| `ingress.enabled`         | Enable ingress controller           | `false`                                                  |
| `ingress.hosts`           | Ingress hosts                       | `[]`                                                     |
| `ingress.annotations`     | Ingress annotations                 | `kubernetes.io/ingress.class: nginx`                     |
| `ingress.tls`             | Ingress tls configuration           | ``                                                       |