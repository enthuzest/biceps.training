# Why we need parameter files?

Application containes many environments and each envrionmnet contanins unqiue inputs/parameter. To resue the same code we create parameter file for each environment.

Parameter files make it easy to specify parameter values together as a set. Within the parameter file, you provide values for the parameters in your Bicep file. Parameter files are created by using the JavaScript Object Notation (JSON) language. You can supply a parameter file when you deploy your Bicep template.

## How to use parameter files?
Run below code in Azure CLI

`az deployment group create --template-file main.bicep --parameters main.parameters.dev.json`