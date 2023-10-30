# Customize Kube-Prometheus 0.12 using Jsonnet

> <https://github.com/prometheus-operator/kube-prometheus/blob/release-0.12/docs/customizing.md>

## Install Kube-Prometheus

```shell
# install jsonnet-bundler and init the project
go install -a github.com/jsonnet-bundler/jsonnet-bundler/cmd/jb@latest
jb init

# first time only
#jb install https://github.com/prometheus-operator/kube-prometheus/jsonnet/kube-prometheus@release-0.12

# consecutive times
jb install

# to update the project
#jb update
```

## Customize Kube-Prometheus

```shell
# get example files
wget https://raw.githubusercontent.com/prometheus-operator/kube-prometheus/release-0.12/example.jsonnet -O example.jsonnet
wget https://raw.githubusercontent.com/prometheus-operator/kube-prometheus/release-0.12/build.sh -O build.sh

# install jsonnet and gojsontoyaml dependencies
go install github.com/google/go-jsonnet/cmd/jsonnet@latest
go install github.com/brancz/gojsontoyaml@latest

# build it
chmod +x ./build.sh
./build.sh example.jsonnet
```
