## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```console
helm repo add openyurt https://openyurtio.github.io/charts
```

If you have already added this repo earlier, run `helm repo update` to retrieve the latest versions of the packages.
You can then run `helm search repo openyurt` to see the charts.

### Install `yurt-manager`

```shell
helm upgrade --install yurt-manager -n kube-system openyurt/yurt-manager
```

### Install `yurthub`

Only the `yurtstaticset` templates and RBAC configurations related to the yurthub component are installed here, whereas the yurthub `static pod` needs to be installed using the `yurtadm join` command.

```shell
helm upgrade --install yurthub -n kube-system openyurt/yurthub
```

### Install `raven-agent`

```shell
helm upgrade --install raven-agent -n kube-system openyurt/raven-agent
