### Usage
1. Deploy External Secret Operator in EKS - more details can be found from [official helm chart](https://artifacthub.io/packages/helm/external-secrets-operator/external-secrets)

2. Make sure all the pods are up and running properly . 

3. Deploy ESO helm chart using the command 
```
helm upgrade release . --install  #The namespace in values.yml should be the one on which you want to have secrets secrets
```

With the current values of yaml file . Below happens

1. The secrets in secret manager with name - /wsp/dummy/awssecretname1 and /wsp/dummy/awssecretname2 will be available as kubernetes secrets with name k8secret1 and k8secret2 in portals namespace

2. The SSM parameters with name - /wsp/dummy/parameterstorename1, /wsp/dummy/parameterstorename2 , /wsp/dummy/parameterstorename3 will be available  under k8 secret name k8secretname1 with respective keys secretkeyname1, secretkeyname2 , secretkeyname3 in portals namesapce

    similarly /wsp/dummy/parameterstorename4 , /wsp/dummy/parameterstorename5 and /wsp/dummy/parameterstorename6 will be available under k8 secret name k8secretname2 with respective keys - secretkeyname4 , secretkeyname5 , secretkeyname6 in portals namespace