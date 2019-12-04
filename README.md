### Happy path
```[bash]
az group create --name tpapp-test --location WestEurope
az group deployment create --resource-group tpapp-test --template-file .\azuredeploy-simple.json --parameters .\azuredeploy-simple.parameters.json
```

### Reproduce error
```[bash]
az deployment create --location WestEurope --template-file .\azuredeploy-reproduce-error.json --parameters .\azuredeploy-reproduce-error.parameters.json
```

Error:
```
Deployment failed. Correlation ID: 41b3c128-d8f1-4586-8ba6-3e8082d6ae08. {
  "error": {
    "code": "InvalidTemplate",
    "message": "Unable to process template language expressions for resource '/subscriptions/.../resourceGroups/tpapp-test/providers/Microsoft.Resources/deployments/storageDeployment' at line '1' and column '507'. 'The template function 'copyIndex' is not expected at this location. The function can only be used in a resource with copy specified. Please see https://aka.ms/arm-copy for usage
details.'",
    "additionalInfo": [
      {
        "type": "TemplateViolation",
        "info": {
          "lineNumber": 1,
          "linePosition": 507,
          "path": ""
        }
      }
    ]
  }
}
```