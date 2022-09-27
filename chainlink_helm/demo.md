# Chainlink node helm chart demo

1. Get access to a Kubernetes cluster; ideally one with an ingress controller like ingress-nginx, plus cert-manager and external-dns.

1. On your computer: Add the linkpool-public-stable chart repo to your repos.
`helm repo add linkpool-public-stable https://public-charts.linkpool.io/stable`

1. After adding the repo, run a repo update.
`helm repo update`

1.  List the available charts from our repo.
```
» helm search repo linkpool-public-stable
NAME                            	CHART VERSION	APP VERSION	DESCRIPTION
linkpool-public-stable/chainlink	0.7.6        	v1.1.0     	A Helm chart for deploying a Chainlink node to ...
```
1. If you want to proceed with the default values, simply install like so:
`helm install linkpool-public-stable/chainlink`

I'll install it with these values like so:
`helm install workshop-node --namespace workshop linkpool-public-stable/chainlink -f example.values.yml`

1. Wait ~1-2 minutes for postgres and the chainlink node to initialize.

```
» k get po -n workshop
NAME                         READY   STATUS    RESTARTS   AGE
workshop-node-0              1/1     Running   2          3m9s
workshop-node-postgresql-0   1/1     Running   0          3m9s

» k get ing -n workshop
NAME            CLASS                    HOSTS                                     ADDRESS         PORTS     AGE
workshop-node   ingress-nginx-external   workshop-node.us-east1.naas.linkpool.io   34.139.76.124   80, 443   3m28s
```

1. The web UI should now be available: https://workshop-node.us-east1.naas.linkpool.io/signin
