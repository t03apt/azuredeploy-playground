### Happy path
```
az group create --name tpapp-test --location WestEurope
az group deployment create --resource-group tpapp-test --template-file .\azuredeploy-simple.json --parameters .\azuredeploy-simple.parameters.json
```

### Reproduce error
```
az deployment create --location WestEurope --template-file .\azuredeploy-reproduce-error.json --parameters .\azuredeploy-reproduce-error.parameters.json
```