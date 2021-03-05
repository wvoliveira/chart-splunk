# chart-splunk

Helm chart for Splunk Enterprise..

Based on [docker-splunk test_scenarios](https://github.com/splunk/docker-splunk).

## Dependencies

- [helm](https://helm.sh/): to install this package
- [kubectl](https://kubernetes.io/docs/tasks/tools/): to use K8s

## Get started

Clone repository and jump to folder project:

```bash
git clone https://github.com/wvoliveira/chart-splunk
cd chart-splunk
```

Install and create namespace if not exists:

```bash
helm install --create-namespace --namespace splunk splunk .
```

Waiting for setup done:

```bash
kubectl logs -f svc/captain
```

When finish, message will be like:

```txt

```
