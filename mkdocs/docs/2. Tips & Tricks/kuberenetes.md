# Kubernetes

## Creating custom kubectl shortcuts

These examples use zsh, but could be easily adapted to bash.

To edit the zsh config file:
```bash
vim ~/.zshrc
```

Note: make sure you restart the terminal after making these updates, or run `zsh` to create a new session.

Here are the aliases I use today:
```bash
alias k=kubectl
alias kdev="kubectl config set-context --current --namespace=dev"
alias kqa="kubectl config set-context --current --namespace=qa"
alias kuat="kubectl config set-context --current --namespace=uat"
alias kgp="kubectl get pods"

kenv() { kubectl config set-context --current --namespace=$1; }
kbash() { kubectl exec --stdin --tty $1 -- /bin/bash; }
```

As you can see, I use alias to create shortcuts for very common commands. If a shortcut requires an argument, you can create a function.

Example usage:

```bash
> kqa
Context "k8s-context" modified.

> kgp
NAME                                  READY   STATUS      RESTARTS   AGE
my-service-99bcfcdf5-9vvkl            1/1     Running     0          25d

> kbash my-service-99bcfcdf5-9vvkl 
root@my-service-99bcfcdf5-9vvkl:/> 
```

## k9s

Consider [k9s](https://k9scli.io/) to simplify kubernetes management tasks including:

- Describing pods
- Executing shell on a pod
- Port forwarding
- Vewing Logs

