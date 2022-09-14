# Full House

A simple web based Planning Poker implementation.

[Full House on GitHub](https://github.com/philmtd/full-house)

## TL;DR

```
$ helm repo add philmtd https://philmtd.github.io/helm-charts
$ helm install my-release philmtd/full-house
```

## Parameters

### Common parameters

| Name                 | Description                               | Value |
| -------------------- | ----------------------------------------- | ----- |
| `nameOverride`       | String to partially override the name     | `""`  |
| `fullnameOverride`   | String to fully override the release name | `""`  |
| `imagePullSecrets`   | Docker registry secret names as an array  | `[]`  |
| `hostAliases`        | Host aliases available to the application | `nil` |
| `resources.limits`   | The resource limits for the container     | `{}`  |
| `resources.requests` | The resource requests for the container   | `{}`  |


### Full House parameters

| Name                              | Description                                                        | Value                |
| --------------------------------- | ------------------------------------------------------------------ | -------------------- |
| `fullhouse.image.name`            | The container image repository                                     | `philmtd/full-house` |
| `fullhouse.image.tag`             | The container image tag, defaults to `Chart.AppVersion` if not set | `""`                 |
| `fullhouse.image.imagePullPolicy` | Image Pull Policy                                                  | `IfNotPresent`       |


### Probes

| Name                                 | Description                              | Value |
| ------------------------------------ | ---------------------------------------- | ----- |
| `startupProbe.failureThreshold`      | Failure threshold for startupProbe       | `10`  |
| `startupProbe.initialDelaySeconds`   | Initial delay seconds for startupProbe   | `0`   |
| `startupProbe.timeoutSeconds`        | Timeout seconds for startupProbe         | `1`   |
| `startupProbe.periodSeconds`         | Period seconds for startupProbe          | `2`   |
| `readinessProbe.failureThreshold`    | Failure threshold for readinessProbe     | `3`   |
| `readinessProbe.initialDelaySeconds` | Initial delay seconds for readinessProbe | `0`   |
| `readinessProbe.timeoutSeconds`      | Timeout seconds for readinessProbe       | `5`   |
| `readinessProbe.periodSeconds`       | Period seconds for readinessProbe        | `1`   |
| `livenessProbe.failureThreshold`     | Failure threshold for livenessProbe      | `3`   |
| `livenessProbe.initialDelaySeconds`  | Initial delay seconds for livenessProbe  | `0`   |
| `livenessProbe.timeoutSeconds`       | Timeout seconds for livenessProbe        | `5`   |
| `livenessProbe.periodSeconds`        | Period seconds for livenessProbe         | `10`  |


### Traffic Exposure parameters

| Name                            | Description                                   | Value  |
| ------------------------------- | --------------------------------------------- | ------ |
| `service.annotations`           | annotations for the service                   | `{}`   |
| `service.type`                  | Kubernetes service type                       | `nil`  |
| `service.sessionAffinity`       | the service's sessionAffinity                 | `None` |
| `service.sessionAffinityConfig` | additional sessionAffinity configuration      | `{}`   |
| `service.loadBalancerIP`        | A loadBalancerIP configuration                | `nil`  |
| `service.clusterIP`             | The service's clusterIP                       | `nil`  |
| `ingress.ingressClassName`      | name of the ingressClass used for the ingress | `nil`  |
| `ingress.hosts`                 | Array with hostnames used for the ingress     | `nil`  |
| `ingress.tls`                   | TLS configuration of the ingress as an array  | `nil`  |
| `ingress.annotations`           | annotations for the ingress                   | `{}`   |


### Metrics

| Name                      | Description                                            | Value   |
| ------------------------- | ------------------------------------------------------ | ------- |
| `serviceMonitor.enabled`  | Whether the serviceMonitor resource should be deployed | `false` |
| `serviceMonitor.interval` | Prometheus scrape interval                             | `10s`   |

