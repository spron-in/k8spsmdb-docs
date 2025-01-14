# Install Percona Server for MongoDB using Helm

[Helm](https://github.com/helm/helm) is the package manager for Kubernetes. Percona Helm charts can be found in [percona/percona-helm-charts](https://github.com/percona/percona-helm-charts) repository on Github.

## Pre-requisites

Install Helm following its [official installation instructions](https://docs.helm.sh/using_helm/#installing-helm).

!!! note

    Helm v3 is needed to run the following steps.

## Installation


1. Add the Percona’s Helm charts repository and make your Helm client up to
    date with it:

    ```bash
    $ helm repo add percona https://percona.github.io/percona-helm-charts/
    $ helm repo update
    ```

2. Install Percona Operator for MongoDB:

    ```bash
    $ helm install my-op percona/psmdb-operator --version {{ release }}
    ```

    The `my-op` parameter in the above example is the name of [a new release object](https://helm.sh/docs/intro/using_helm/#three-big-concepts)
    which is created for the Operator when you install its Helm chart (use any
    name you like).

    !!! note

        If nothing explicitly specified, `helm install` command will work
        with `default` namespace. To use different namespace, provide it with
        the following additional parameter: `--namespace my-namespace`.

3. Install Percona Server for MongoDB:

    ```bash
    $ helm install my-db percona/psmdb-db --version {{ release }} --namespace my-namespace
    ```

    The `my-db` parameter in the above example is the name of [a new release object](https://helm.sh/docs/intro/using_helm/#three-big-concepts)
    which is created for the Percona Server for MongoDB when you install its Helm
    chart (use any name you like).

## Installing Percona Server for MongoDB with customized parameters

The command above installs Percona Server for MongoDB with [default parameters](operator.md#operator-custom-resource-options).
Custom options can be passed to a `helm install` command as a
`--set key=value[,key=value]` argument. The options passed with a chart can be
any of the Operator’s [Custom Resource options](https://github.com/percona/percona-helm-charts/tree/main/charts/psmdb-db#installing-the-chart).

!!! note

    Parameters from the [Replica Set section](operator.md#operator-replsets-section)
    are treated differently: if you specify *any* parameter from replsets<operator.replsets-section>,
    the Operator *will not* use default values for this Replica Set.
    So do not specify Replica Set options at all or specify all needed options
    for the Replica Set.

The following example will deploy a Percona Server for MongoDB Cluster in the
`psmdb` namespace, with disabled backups and 20 Gi storage:

```bash
$ helm install my-db percona/psmdb-db --version {{ release }} --namespace psmdb \
  --set "replsets[0].name=rs0" --set "replsets[0].size=3" \
  --set "replsets[0].volumeSpec.pvc.resources.requests.storage=20Gi" \
  --set backup.enabled=false --set sharding.enabled=false
```
