## Install requirement before using Ansible AKS module
```bash
pip install azure-mgmt-containerservice>=3.0.1
```

## Use ansible to create AKS
refer the [demo](./create_scale_aks.yml), enter your own client id/secret and ssh public key in the var part. And then run the playbook.

## Use ansible to scale the existing AKS

### Use AZ-CLI to get the information of the existing AKS
```bash
az aks show -g <your-rg> -n <aks-name>
```

1. You can get the following json
  ```json
  {
    "additionalProperties": {},
    "agentPoolProfiles": [
      {
        "additionalProperties": {},
        "count": 2,
        "name": "agentpool",
        "osType": "Linux",
        "storageProfile": "ManagedDisks",
        "vmSize": "Standard_DS2_v2"
      }
    ],
    "dnsPrefix": "XXXXXXXXXX",
    "fqdn": "XXXXXXXXXX.hcp.eastus.azmk8s.io",
    "id": "/subscriptions/XXXXXXXXXXXXXXXXXXXXXXXXX/resourcegroups/XXXXXXXXXXXXXXXX/providers/Microsoft.ContainerService/managedClusters/XXX",
    "kubernetesVersion": "1.8.1",
    "linuxProfile": {
      "additionalProperties": {},
      "adminUsername": "azureuser",
      "ssh": {
        "additionalProperties": {},
        "publicKeys": [
          {
            "additionalProperties": {},
            "keyData": "************************************"
          }
        ]
      }
    },
    "location": "eastus",
    "name": "XXX",
    "provisioningState": "Succeeded",
    "resourceGroup": "XXXXXXXX",
    "servicePrincipalProfile": {
      "additionalProperties": {},
      "clientId": "************************"
    },
    "type": "Microsoft.ContainerService/ManagedClusters"
  }
  ```

2. Find the corresponding field value to replace the value in [playbook](./create_scale_aks.yml).

3. Run the playbook, it should return immediately with no change, that means all parameters are correct.

4. Update the agentpool count, re-run the playbook, wait 20 mins to see your AKS is scaled.
