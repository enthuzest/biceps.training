# Conditions
## Examples
### Example 1
```
resource storageAccount 'Microsoft.Storage/storageAccounts@2021-09-01' = if (deployStorageAccount) {
```

### Example 2
```
resource auditingSettings 'Microsoft.Sql/servers/auditingSettings@2021-11-01-preview' = if (environmentName == 'Production') {
```

# Loops
## Examples

### Example 1
```
param storageAccountNames array = [
  'saauditus'
  'saauditeurope'
  'saauditapac'
]

resource storageAccountResources 'Microsoft.Storage/storageAccounts@2021-09-01' = [for storageAccountName in storageAccountNames: {
  name: storageAccountName
  location: resourceGroup().location
  kind: 'StorageV2'
  sku: {
    name: 'Standard_LRS'
  }
}]
```

### Example 2
```
resource storageAccountResources 'Microsoft.Storage/storageAccounts@2021-09-01' = [for i in range(1,4): {
```