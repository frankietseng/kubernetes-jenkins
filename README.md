# Jenkins on Kubernetes

使用Kuberntes建立Jenkins。

# Running
#### 1. 建立存儲區
```
kubectl create -f jenkins-hostpath.yml
kubectl create -f jenkins-pvc.yml
```
#### 2. 新增Repo
```sh
helm repo add stable https://kubernetes-charts.storage.googleapis.com
```
#### 3. 啟動Jenkins
```sh
helm install jenkins --set persistence.existingClaim=jenkins-pvc stable/jenkins -f jenkins-values.yml
```

