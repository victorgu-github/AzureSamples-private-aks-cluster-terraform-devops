# remove custom script and relate variables 
 # script_storage_account_name         = var.script_storage_account_name
  # script_storage_account_key          = var.script_storage_account_key
  # container_name                      = var.container_name
  # script_name                         = var.script_name

cd terraform
terraform init -backend-config backend.conf