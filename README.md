# Here's how to install and run the Dynatrace Logs Workshop!

## Workshop Format
* This workshop is intended to be a hands on introduction to Logs on latest Dynatrace platform.
  * The material can be broken down modularly as required for your use case
  * The target personas are - 1) Dynatrace users, 2) Dynatrace Admins
  * Presentation is broken down into 2 parts to cater to the above 2 personas
* Audience: Existing Dynatrace customers and late stage prospects (Intermediate Level Workshop).
* Time: 2.5-4 Hours depending on how many labs you want to cover.
* Present a 60 minute "Logs Workshop" presentation.
  * PDF copy attached in the repo
  * PPTX linked here - https://dynatrace-my.sharepoint.com/:p:/p/rohan_shah/Ee56t0nDQRVJlnv0YnxphogB150NiprfgzZiGSKzxXZYVQ?e=o6v6a6
* Get everyone logged in and run through the Workshop:
  * Dynatrace User - Workshop Exercises
  * Dynatrace User - Workshop Answer Key


## Requirements
* Dynatrace SaaS Tenant (with latest Dynatrace/Grail)
* K8s cluster
  * Tested Specs: 3 Nodes	24 vCPU	96 GB	RAM

## Setup
* Spin up a K8s cluster on a platform of your liking
* Install the DT Operator to your K8s cluster by following these steps within the new K8s app in Dynatrace SaaS:

![](https://raw.githubusercontent.com/rohanshah-sre/LogsWorkshop/refs/heads/main/docs/imgs/K8sDTMonitoring.png)


* Clone Git Repo
```
git clone https://github.com/rohanshah-sre/LogsWorkshop.git
```

* Install OpenTelemetry Demo, EasyTrade, and HipsterShop App

```
kubectl create namespace easytrade
kubectl apply -f ./easytrade/manifests

kubectl create namespace hipstershop
kubectl apply -f ./hipstershop/manifests

kubectl apply --namespace otel-demo -f https://raw.githubusercontent.com/open-telemetry/opentelemetry-demo/main/kubernetes/opentelemetry-demo.yaml
