1. k3d cluster create --api-port 6550 -p "8081:80@loadbalancer" --agents 2
2. helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
   helm repo update
   helm install -n kube-system prom prometheus-community/kube-prometheus-stack
3. install argo rollouts
```bash
kubectl create namespace argo-rollouts
kubectl apply -n argo-rollouts -f https://github.com/argoproj/argo-rollouts/releases/latest/download/install.yaml
```
3. kubectl argo rollouts dashboard

4. install argo cd
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

6. kubectl apply -k ./examples/canary





links:
1. http://localhost:3100/rollout/canary-demo
2. http://canary.localdev.me:8081/
3. http://canary-preview.localdev.me:8081/