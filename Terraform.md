# Terraform Cheatsheet
---
## Setup
-  Install Terraform: https://learn.hashicorp.com/tutorials/terraform/install-cli

## Get it running
- Go to the folder that has your \*.tf files.  Initialize Terraform: ``terraform init``
	- Terraform init to tell Terraform to scan the code, figure out which providers you’re using, and download the code for them. By default, the provider code will be downloaded into a .terraform folder.
	- Terraform will also record information about the provider code it downloaded into a .terraform.lock.hcl file.

## Test your code and apply
- ``terraform plan``
	- The plan command lets you see what Terraform will do before actually making any changes. 
- ``terraform apply`
	- Type in yes, that you approve the plan and want to proceed.

## Debug problems
- export TF_LOG=TRACE

- "Error: error configuring Terraform AWS Provider: no valid credential sources for Terraform AWS Provider found."
	- 
- Error: Too many command line arguments
	- You have many .tf files in your directory. You have to tell terraform which one to use. ``terraform plan -out=ec2-web-sec.tf``

## Dependency graph
- ``terraform graph``
	- When you add a reference from one resource to another, you create an implicit dependency. Terraform parses these dependencies, builds a dependency graph from them, and uses that to automatically determine in which order it should create resources.
