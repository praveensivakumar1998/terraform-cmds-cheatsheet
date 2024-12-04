# terraform-cmds-cheatsheet

![image](https://github.com/user-attachments/assets/6302c77d-181d-4550-af15-a1bac63ef3a2)


### Here are commonly used Terraform commands along with their explanations:

## 1. terraform init

***Purpose:*** Initializes a Terraform working directory.

***Usage:***   Run before any other Terraform command.

***Details:***
  * Downloads the required provider plugins.
  * Prepares the backend configuration if specified.
  * Sets up the working directory for further operations.

```
terraform init
```

## 2. terraform plan

***Purpose:*** Creates an execution plan, showing what changes Terraform will make to achieve the desired state.

***Usage:*** Use it to preview changes before applying them.

***Details:***
  * Does not make any changes to infrastructure.
  * Highlights resources to be added, changed, or destroyed.
```
terraform plan
```
## 3. terraform apply

***Purpose:*** Applies the changes required to reach the desired state of the configuration.

***Usage:*** Executes the plan to create, update, or delete resources.

***Details:***
  * Prompts for confirmation unless -auto-approve is specified.
  * Writes the updated state to the state file.
```
terraform apply
```

## 4. terraform destroy

***Purpose:*** Destroys all resources managed by the current Terraform configuration.

***Usage:*** Use it to clean up all resources.

***Details:***
  * Prompts for confirmation unless -auto-approve is used.
  * Useful for testing or cleanup.
```
terraform destroy
```

## 5. terraform output

***Purpose:*** Displays the values of outputs defined in the configuration.

***Usage:*** Use it to retrieve information about your infrastructure.
```
terraform output
```

## 6. terraform validate

***Purpose:*** Validates the syntax and structure of your Terraform configuration files.

***Usage:*** Ensures that the configuration files are syntactically valid before applying.
```
terraform validate
```

## 7. terraform fmt

***Purpose:*** Formats Terraform configuration files in a canonical style.

***Usage:*** Use it to ensure consistent formatting.
```
terraform fmt
```

## 8. terraform show

***Purpose:*** Displays the state or execution plan in a human-readable format.

***Usage:*** Useful for debugging and reviewing the current state.
```
terraform show
```
## 9. terraform state

***Purpose:*** Interacts with the state file directly.

***Subcommands:***
```
terraform state list:   Lists all resources in the state file.
terraform state show <resource>:   Shows details of a specific resource.
terraform state mv <source> <destination>:   Moves a resource within the state file.
terraform state rm <resource>:   Removes a resource from the state file.
```
```
terraform state list
```

## 10. terraform import

***Purpose:*** Imports existing infrastructure into Terraform state.

***Usage:*** Use it to manage resources created outside Terraform.
```
terraform import <resource_type>.<resource_name> <resource_id>
```
**Example:**
```
terraform import aws_instance.example i-1234567890abcdef
```

## 11. terraform taint

***Purpose:***  Marks a resource for recreation during the next terraform apply.

***Usage:*** Use it to force the recreation of a resource.
```
terraform taint <resource_type>.<resource_name>
```

## 12. terraform untaint

***Purpose:***  Removes the taint from a resource.

***Usage:*** Use it to prevent the resource from being recreated.
```
terraform untaint <resource_type>.<resource_name>
```

## 13. terraform refresh

***Purpose:***  Updates the state file to reflect the actual infrastructure.

***Usage:*** Useful to ensure the state file matches the real-world state.
```
terraform refresh
```

## 14. terraform providers

***Purpose:*** Displays the providers required for the configuration.

***Usage:*** Use it to verify provider configurations.
```
terraform providers
```

## 15. terraform workspace

***Purpose:*** Manages multiple environments (workspaces) in Terraform.

***Subcommands:***
```
terraform workspace list:   Lists all workspaces.
terraform workspace new <name>:   Creates a new workspace.
terraform workspace select <name>:   Switches to a specified workspace.
```
```
terraform workspace list
```

## 16. terraform graph

***Purpose:*** Generates a visual graph of the dependency tree.

***Usage:*** Can be visualized using tools like Graphviz.
```
terraform graph | dot -Tsvg > graph.svg
```

## 17. terraform lock

***Purpose:*** Manages the dependency lock file.

***Usage:*** 
  * terraform lock file: Creates or updates the .terraform.lock.hcl file.
  * Ensures consistent provider versions across environments.
```
terraform lock file
```

## 18. terraform unlock

***Purpose:*** Unlock the terraform state file if lock exists

***Usage:*** terraform state file lock in some of rare scenarios, user's could not do any list, create or delete resources if the terraform state locks
```
terraform force-unlock <lock-id>
```
