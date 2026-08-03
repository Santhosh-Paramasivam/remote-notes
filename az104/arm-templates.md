---
id: azure-cloud-shell.md
aliases: []
tags:
  - #azure
  - #az-104
  - #az104
  - #cloud
  - #cloud-components
---

# ARM Templates

- [arm-templates](https://learn.microsoft.com/en-us/training/modules/create-azure-resource-manager-template-vs-code/2-explore-template-structure?tabs=azure-cli)

- Declarative, JSON

- ARM Templates are *idempotent*, as in a specific template always produces the same resulting infrastructure

- Resource Manager ensures that resources are created in the correct order.

- Typically faster than scripted deployments

- Resource Manager with Built-in validation

- Templates can be organized more easily

- Easily integrated into DevOps workflows through Azure Pipelines

## Structure of an ARM template 

- **schema:** A required section that defines the location of the JSON schema file that describes the structure of JSON data. The version number you use depends on the scope of the deployment and your JSON editor.

- **contentVersion:** A required section that defines the version of your template (such as 1.0.0.0). You can use this value to document significant changes in your template to ensure you're deploying the right template.

- **apiProfile:** An optional section that defines a collection of API versions for resource types. You can use this value to avoid having to specify API versions for each resource in the template.

- **parameters:** An optional section where you define values that are provided during deployment. You can provide these values in a parameter file, by command-line parameters, or in the Azure portal.

- **variables:** An optional section where you define values that are used to simplify template language expressions.

- **functions:** An optional section where you can define user-defined functions that are available within the template. User-defined functions can simplify your template when complicated expressions are used repeatedly in your template.

- **resources:** A required section that defines the actual items you want to deploy or update in a resource group or a subscription.

- **output:** An optional section where you specify the values that are returned at the end of the deployment.

## Deploy an ARM template

```bash
az login
```

```bash
az group create --name {name of your resource group} --location "{location}"
```

```bash
templateFile="{provide-the-path-to-the-template-file}"
az deployment group create \
  --name blanktemplate \
  --resource-group myResourceGroup \
  --template-file $templateFile
```

Basic template without any resources:

```bash
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {},
  "functions": [],
  "variables": {},
  "resources": [],
  "outputs": {}
}
```