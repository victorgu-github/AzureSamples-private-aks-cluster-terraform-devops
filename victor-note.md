# remove custom script and relate variables 
 # script_storage_account_name         = var.script_storage_account_name
  # script_storage_account_key          = var.script_storage_account_key
  # container_name                      = var.container_name
  # script_name                         = var.script_name

# change k version to 1.29
# give unique name for acr and kv

# dependency_agent common out. already exist!
cd terraform
terraform init -backend-config backend.conf

# get aks id

az aks show --resource-group BaboRG --name BaboAks --query id 


# assignee is your ad group object id
# scope is aks id
az role assignment create --assignee b939cadf-7b93-4f6d-95c4-9e9352b755d3 --role "Azure Kubernetes Service RBAC Cluster Admin" --scope /subscriptions/c7936011-6c67-4e5d-b9c2-a2fafe6ce3e3/resourcegroups/BaboRG/providers/Microsoft.ContainerService/managedClusters/BaboAks

other built roles, https://learn.microsoft.com/en-us/azure/aks/manage-azure-rbac#create-role-assignments-for-users-to-access-the-cluster
Azure Kubernetes Service RBAC Reader
Azure Kubernetes Service RBAC Writer
Azure Kubernetes Service RBAC Admin
Azure Kubernetes Service RBAC Cluster Admin
