# kubectl-tmux-logs

## About

### Description
A kubectl plugin to display container logs within separate tmux panes

### Installation
Add `kubectl-tmux-logs` to your `kubectl` plugins directory. For more information about how plugins are loaded, please see the [official documentation](https://kubernetes.io/docs/tasks/extend-kubectl/kubectl-plugins/).
```
git clone git@github.com:brosandilabs/kubectl-tmux-logs.git ~/.kube/plugins/kubectl-tmux-logs
```

### Usage

```
> kubectl plugin tmux-logs --help
tmux-logs integrates kubectl logs with tmux by opening a new pane for each pod-container log

Options:
  -c, --container='': Container name (for pods with multiple containers)
  -l, --selector='': Selector (label query) to filter on, supports '=', '==', and '!='.(e.g. -l key1=value1,key2=value2)

Usage:
  kubectl plugin tmux-logs [flags] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).

```

### Examples
Get logs from all containers in the "my-namespace" namespace:
```
kubectl plugin tmux-logs -n my-namespace
```

Get logs from all containers in pods matching the "name=my-pod" selector in the "my-namespace" namespace:
```
kubectl plugin tmux-logs -l name=my-pod -n my-namespace
```

Get logs from a specific container in pods with "app=my-app" label:
```
kubectl plugin tmux-logs -l app=my-app -c some-container-name
```
