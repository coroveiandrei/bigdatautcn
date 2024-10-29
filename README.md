## Step 1 Create Azure Subcription

If you don't have an active Azure Subscription, you can create one at:
https://azure.microsoft.com/en-us/free/

Connect to portal.azure.com and create a new resource group called [yourname]

## Step 2 Install Azure CLI & login to Azure

Install Azure CLI from here https://learn.microsoft.com/en-us/cli/azure/install-azure-cli
Open up vscode and from the terminal run:
2.1 az login
2.2 az account set -n  "SUBSCRIPTION_NAME_FROM_PORTAL" 

## Step 3 Deploy Storage from Bicep template

1. Open up visual studio code
2. Open up folder infracode in vs code
3. In storageparams.json, line 8, replace the name of the storage account with: "[yourname]stor"
4. In VSCode terminal, run the commands:


az deployment group what-if --resource-group  [yourname] --template-file 1storage.bicep --parameters .\config\storageparams.json
This command will only show you what happens in case of a deployment

Now create the actual resources

az deployment group create  --resource-group  [yourname] --template-file 1storage.bicep --parameters .\config\storageparams.json

