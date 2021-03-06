---
title: "Education Lab"
author: "github.com/danielehc"
slug: "learn-consul-service-mesh"
browser_windows: "http://localhost:18443"
---

## Setup kubectl
Set the following environment variables to interact with this blueprint.

```
export KUBECONFIG="$HOME/.shipyard/config/k8s/kubeconfig.yaml"
```

## Kubernetes dashboard
To access the Kubernetes dashboard visit the following location in your browser:    

```
http://localhost:18443
```

Note: authentication is disabled, press "Skip" when prompted

## Consul
Set the following environment variables to interact with Consul datacenter 

```
export CONSUL_HTTP_ADDR="http://localhost:18500"
```

Note: By default Consul is not deployed. You can deploy it with:

```
helm install hashicorp ./helm-charts/consul-helm-0.16.2 -f ./helm-charts/consul-values.yml
```

## Consul UI

To access the Consul UI visit the following location in your browser:

```
http://localhost:18500
```

Note: by default Consul UI service is not accessible externally. To enable access:

```
shipyard run ./ingresses/consul-ui.hcl
```

# Cleanup

Run `shipyard destroy` to cleanup all resources