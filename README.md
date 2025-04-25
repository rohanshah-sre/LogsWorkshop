# Here's how to install and run the Dynatrace Platform Workshop!

## Workshop Format
* This workshop is intended to be a hands on introduction to Logs on latest Dynatrace platform.
* Audience: Existing Dynatrace customers and late stage prospects (Intermediate Level Workshop).
* Time: 2.5-4 Hours depending on how many labs you want to cover.
* Present a 60 minute "Logs Workshop" presentation.
* Get everyone logged in and run through the Workshop:
  * Dynatrace User - Workshop Exercises
  * Dynatrace User - Workshop Answer Key


## Requirements
* Dynatrace SaaS Tenant (with latest Dynatrace/Grail)
  * Dynatrace AppSec RVA Turned On: https://docs.dynatrace.com/docs/shortlink/vulnerability-analytics
* K8s cluster
  * Tested Specs: 3 Nodes	24 vCPU	96 GB	RAM
  * You could probably get away with a smaller cluster. I recently removed EasyTravel and the labs only use EasyTrade and HipsterShop, but I have not yet tested this with less resources.
* Free Tier Slack Account (For Release Evaluation Lab)
  * Sign up for one with a personal email here: https://slack.com/get-started#/createnew

## Setup
* Spin up the K8s cluster and configure outbound rules for OneAgent traffic
* Install the OneAgent Operator and connect the K8s integration
* Clone Git Repo
  
```
git clone https://github.com/JasonOstroski/platformworkshop2023.git
```

* Install OpenTelemetry Demo, EasyTrade, and HipsterShop App

```
kubectl create namespace easytrade
kubectl apply -f ./easytrade/manifests

kubectl create namespace hipstershop
kubectl apply -f ./hipstershop/manifests

kubectl apply --namespace otel-demo -f https://raw.githubusercontent.com/open-telemetry/opentelemetry-demo/main/kubernetes/opentelemetry-demo.yaml
