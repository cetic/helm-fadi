Contributing to FADI
==========

Merging a pull request
--------------

Check out the PR locally: 

```
# Get this chart
git clone https://github.com/cetic/helm-fadi.git
cd helm-fadi
gh pr checkout 46 # or git checkout -b feature/...

# Better to use a newly create minikube cluster
minikube delete
minikube start --cpus 6 --memory 12288 --disk-size=40GB

# Install deps
kubectl create namespace fadi
helm repo add cetic https://cetic.github.io/helm-charts/ --force-update
helm repo update
helm dep up

# Install FADI
helm upgrade --install fadi -f ./values.yaml --namespace fadi
```

To check on the deployment progress:

```
kubectl get po -n fadi --watch
```


Follow the (adapted) [USERGUIDE](https://github.com/cetic/fadi/blob/master/USERGUIDE.md)
