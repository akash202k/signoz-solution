# Signoz Cloud Observability Demo

> Note: We need to create an apikey for our demo in signoz cloud . You can create one by going to signoz console --> Account setting --> Ingestion --> Create Key.  
Keep handy apikey and Ingestion url.

# Steps

## Download values file for this project

```bash
wget -O signoz-values.yaml \
  https://raw.githubusercontent.com/akash202k/signoz-solution/main/signoz-values.yaml
``` 
> **Note:** Update the Ingestion URL and ApiKey in the values file.  
> You can also add the ApiKey via a Kubernetes secret: create a secret with key `signoz-apikey` and value as your copied API key, then update the secret name in the values file.

## Add signoz helm chart into repo
```bash
helm repo add signoz https://charts.signoz.io
helm repo update
```

## Install helm chart into the cluster 

```bash
helm upgrade --install -n signoz --create-namespace "my-release" signoz/k8s-infra -f signoz-values.yaml
```


> Explore metrics in signoz dashboard



# Architecture and Flow

![alt text](signoz.png)


