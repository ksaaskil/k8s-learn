# KNative quickstart

Follow the [Getting started](https://knative.dev/docs/getting-started/).

Optionally, install `kn` command-line tool from [releases page](https://github.com/knative/client/releases) or using `brew`.

[Install KNative Serving](https://knative.dev/docs/install/serving/install-serving-with-yaml/) component.

Add a service:

```bash
$ kubectl apply -f hello.yaml
```

See the `ksvc`:

```bash
$ kubectl get ksvc
```

You see something like this:

```
NAME    URL                                LATESTCREATED   LATESTREADY   READY   REASON
hello   http://hello.default.example.com   hello-world     hello-world   True
```