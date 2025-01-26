### This repo consists of subset of different Helm Charts I have written.
I try to make these helm charts better whenever I get time 

### Basic Helm Chart Commands

1. Intialize Helm chart 
```
helm create <helm-chartname>
```
2. Validate Helm Chart
```
helm lint /path/to/helm/chart 

helm template [NAME] [CHART] > output.yaml # This gives the final helm chart that is deployed to k8
```
3. Deploy helm chart 
```
helm upgrade [RELEASE_NAME] [CHART] --install --namespace [NAMESPACE]
```

#### List of Helm Charts with small Description

1. [ESO - External Secrets Operator](./eso/Readme.md)

This is a helm chart to deploy on an EKS cluster once ESO is installed
This helm chart will create 
-  External Secret Store for SecretManager and SSM parameter store
- Creates External Secrets from a list of secret manager secrets or ssm parameter store
- This helm chart uses conditional block like if else , range and index of template syntax.

Note - This helm chart will use IAM Node Role policy attached to EKS nodes

To Dos : 
- [ ] Add ability to have different prefix for secret manager and ssm parameter store
- [ ] Flexibility to use ServiceAccount to which IAM role is associated

