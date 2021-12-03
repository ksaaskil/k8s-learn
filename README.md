# Learn Kubernetes

## Argo

Start `minikube`:

```bash
$ minikube start
$ kubectl config use-context minikube
```

Install and expose Argo:

```bash
$ kubectl create namespace argo
$ kubectl apply -n argo -f argo/quick-start-postgres.yaml
$ kubectl -n argo port-forward deployment/argo-server 2746:2746
```

Install [Argo CLI](https://github.com/argoproj/argo-workflows/releases) and launch an example job:

```bash
$ argo submit -n argo --watch argo/hello-world.yaml
$ argo list -n argo
$ argo get -n argo @latest
$ argo logs -n argo @latest
```

Parametrized job:

```bash
$ argo submit -n argo argo/hello-parameters.yaml -p message="goodbye world"
$ argo submit -n argo argo/hello-parameters.yaml --parameter-file argo/parameters.yaml
```

## Resources

```bash
$ kubectl create namespace mem-example
$ kubectl apply -f pods/resource/memory-request-limit.yaml -n mem-example
$ kubectl get pod memory-demo -n mem-example --output=yaml
$ kubectl delete pod memory-demo -n mem-example
```

```bash
$ kubectl create namespace cpu-example
$ kubectl apply -f pods/resource/cpu-request-limit.yaml -n cpu-example
$ kubectl get pod cpu-demo -n mem-example --output=yaml
$ kubectl delete pod cpu-demo -n cpu-example
```
