# terraform-google-solution-builder-vpc-network

## Description
### Tagline
Google Cloud Virtual Private Cloud (VPC) provides networking functionality to Compute Engine virtual machine (VM) instances, Google Kubernetes Engine (GKE) containers, and serverless workloads.

### Detailed
This composition unit creates a VPC network in the provided GCP Project. Additionally, it also creates a private service connection for this VPC network to be able to connect to Google owned services like Cloud SQL. It also creates a VPC access connector which makes it possible to connect to this VPC network from serverless environments like Cloud Run, App Engine and Cloud Functions.

The resources/services/activations/deletions that this module will create/trigger are:

- Create a VPC network in the provided GCP project.
- Create a private service connection for this VPC network.
- Create a serverless VPC access connector.

### PreDeploy
To deploy this blueprint you must have an active billing account and billing permissions.

## Documentation
- [VPC network](https://cloud.google.com/vpc/docs/overview)

## Cost
[Blueprint cost details](https://cloud.google.com/products/calculator/?utm_source=google&utm_medium=cpc&utm_campaign=japac-IN-all-en-dr-BKWS-all-hv-trial-EXA-dr-1605216&utm_content=text-ad-none-none-DEV_c-CRE_634320843821-ADGP_Hybrid%20%7C%20BKWS%20-%20EXA%20%7C%20Txt%20~%20Compute_Compute%20Engine_google%20virtual%20machine_cost-KWID_43700074201065744-aud-970366092687%3Akwd-419589539210&userloc_9061993-network_g&utm_term=KW_google%20vm%20pricing%20calculator&gad_source=1&gclid=CjwKCAiAopuvBhBCEiwAm8jaMW48oZ9B3NSbDmsUQf6JyntbYNktIlJlOIYUOJvZBKMhm39vEhioORoC38gQAvD_BwE&gclsrc=aw.ds&hl=en&dl=CiQ4MGJjNzRiNy0wOTEzLTQ5MTItODI0Zi1mZDc0NDAzZGY5NzQQDhokRkRDRDdEQjMtOTE1NS00OENFLUI1NjctM0JEODg0MkY4OTU4)

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

## Requirements

These sections describe requirements for using this module.

### Software

The following dependencies must be available:

- [Terraform][terraform] v0.13
- [Terraform Provider for GCP][terraform-provider-gcp] plugin v3.0

### Service Account

A service account with the following roles must be used to provision
the resources of this module:

- Compute Network Admin: `roles/compute.networkAdmin`
- Service Networking Service Agent: `roles/servicenetworking.serviceAgent`
- Serverless VPC Access Admin : `roles/vpcaccess.admin`

The [Project Factory module][project-factory-module] and the
[IAM module][iam-module] may be used in combination to provision a
service account with the necessary roles applied.

### APIs

A project with the following APIs enabled must be used to host the
resources of this module:

- Serverless VPC Access API: `vpcaccess.googleapis.com`
- Service Networking API: `servicenetworking.googleapis.com`

The [Project Factory module][project-factory-module] can be used to
provision a project with the necessary APIs enabled.

## Contributing

Refer to the [contribution guidelines](./CONTRIBUTING.md) for
information on contributing to this module.

[iam-module]: https://registry.terraform.io/modules/terraform-google-modules/iam/google
[project-factory-module]: https://registry.terraform.io/modules/terraform-google-modules/project-factory/google
[terraform-provider-gcp]: https://www.terraform.io/docs/providers/google/index.html
[terraform]: https://www.terraform.io/downloads.html

## Security Disclosures

Please see our [security disclosure process](./SECURITY.md).
