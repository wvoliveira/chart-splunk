# chart-splunk

[![Lint and Test Charts](https://github.com/wvoliveira/chart-splunk/actions/workflows/lint-test.yml/badge.svg?branch=main)](https://github.com/wvoliveira/chart-splunk/actions/workflows/lint-test.yml)

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

Add your developer License in `mySplunkLicense.lic` file:

```bash
cat `license file path` > data/nginx/nginx-data-www/mySplunkLicense.lic
```

Install and create namespace if not exists:

```bash
helm install --create-namespace --namespace splunk splunk .
```

Change to `splunk` namespace:

```bash
kubectl config set-context --current --namespace=splunk
```

Waiting for setup done:

```bash
kubectl logs -f svc/captain
```

When finish, message will be like:

```txt
Ansible playbook complete, will begin streaming splunkd_stderr.log
```

Now export the node port from minikube to access web UI:

```bash
minikube service search -n splunk
```

And that's it. Your cluster is ready!
