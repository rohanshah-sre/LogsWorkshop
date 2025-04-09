# LogsWorkshop

## Setup
* Spin up the K8s cluster and configure outbound rules for OneAgent traffic
* Install the OneAgent Operator and connect the K8s integration
* Clone Git Repo
  
```
git clone https://github.com/JasonOstroski/platformworkshop2023.git
```

* Install EasyTrade and HipsterShop

```
kubectl create namespace easytrade
kubectl apply -f ./easytrade/manifests

kubectl create namespace hipstershop
kubectl apply -f ./hipstershop/manifests
