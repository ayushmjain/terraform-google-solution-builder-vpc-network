# Simple Example

This example illustrates how to use the `solution-builder-vpc-network` module.

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| network\_name | VPC network name | `string` | n/a | yes |
| project\_id | GCP project ID where the VPC network is created | `string` | n/a | yes |
| region | GCP region for creating VPC access connector that can be used by serverless services like cloud run to access this VPC network | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| network\_name | n/a |
| private\_services\_connection\_dependency | n/a |
| vpc\_access\_connector\_id | n/a |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

To provision this example, run the following from within this directory:
- `terraform init` to get the plugins
- `terraform plan` to see the infrastructure plan
- `terraform apply` to apply the infrastructure build
- `terraform destroy` to destroy the built infrastructure
