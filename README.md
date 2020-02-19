# k8s resources

Kubernetes resources i.e. notes and scripts which might be useful to others as well

## Delete multiple namespaces in state `Terminating`

Use the script [`kill-kube-ns.sh](./kill-kube-ns.sh) from Redhat as follows

```bash
kubectl get ns | awk '/Term/ { print $1 }' | while IFS= read -r line; do ~/bin/kill-kube-ns.sh $line; done
```

Reference is [this post at stackoverflow.com](https://stackoverflow.com/questions/60230242/how-to-output-the-result-of-a-chain-of-commands-for-a-given-input-with-bash/60303522#60303522)
