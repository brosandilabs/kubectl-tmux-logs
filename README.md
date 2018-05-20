# kubectl-tmux-logs

## About

### Description
A kubectl plugin to display container logs within separate tmux panes

### Installation
Add `kubectl-tmux-logs` to your `kubectl` plugins directory. For more information about how plugins are loaded, please see the [official documentation](https://kubernetes.io/docs/tasks/extend-kubectl/kubectl-plugins/).
```
git clone git@github.com:normanjoyner/kubectl-tmux-logs.git ~/.kube/plugins/kubectl-tmux-logs
```

### Usage
Get logs from all pods in the "my-namespace" namespace:
```
kubectl plugin tmux-logs -n my-namespace
```

Get logs from pods matching the "name=my-pod" selector in the "my-namespace" namespace:
```
kubectl plugin tmux-logs -l name=my-pod -n my-namespace
```
