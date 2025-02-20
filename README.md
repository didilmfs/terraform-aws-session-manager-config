# terraform-aws-session-manager-config

[![Terraform Version](https://img.shields.io/badge/Terraform%20Version->=0.12.0,<0.13.0-blue.svg)](https://releases.hashicorp.com/terraform/)
[![Release](https://img.shields.io/github/release/traveloka/terraform-aws-session-manager-config.svg)](https://github.com/traveloka/terraform-aws-session-manager-config/releases)
[![Last Commit](https://img.shields.io/github/last-commit/traveloka/terraform-aws-session-manager-config.svg)](https://github.com/traveloka/terraform-aws-session-manager-config/commits/master)
[![Issues](https://img.shields.io/github/issues/traveloka/terraform-aws-session-manager-config.svg)](https://github.com/traveloka/terraform-aws-session-manager-config/issues)
[![Pull Requests](https://img.shields.io/github/issues-pr/traveloka/terraform-aws-session-manager-config.svg)](https://github.com/traveloka/terraform-aws-session-manager-config/pulls)
[![License](https://img.shields.io/github/license/traveloka/terraform-aws-session-manager-config.svg)](https://github.com/traveloka/terraform-aws-session-manager-config/blob/master/LICENSE)
![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)

## Description

This terraform module creates configuration for session manager preferences or logging. 


## Table of Content
- [Description](#description)
- [Table of Content](#table-of-content)
- [Dependencies](#dependencies)
- [Terraform Version](#terraform-version)
- [Authors](#authors)
- [Requirements](#requirements)
- [Providers](#providers)
- [Modules](#modules)
- [Resources](#resources)
- [Inputs](#inputs)
- [Outputs](#outputs)
- [Contributing](#contributing)
- [License](#license)


## Dependencies

This Terraform module have no dependencies to another modules


## Terraform Version
This module was created on 03/14/2019. The latest stable version of Terraform which this module tested working is Terraform 0.12.31 on 16/09/2021


## Authors
* [Bernard](https://github.com/SiahaanBernard)


<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.12 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 1.36.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 1.36.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_iam_policy.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_policy) | resource |
| [aws_s3_bucket.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket) | resource |
| [aws_s3_bucket_policy.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket_policy) | resource |
| [aws_s3_bucket_public_access_block.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket_public_access_block) | resource |
| [aws_ssm_document.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ssm_document) | resource |
| [aws_caller_identity.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity) | data source |
| [aws_iam_policy_document.s3_bucket](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_iam_policy_document.session_manager](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_iam_role.super_admin](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_role) | data source |
| [aws_region.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/region) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_environment"></a> [environment](#input\_environment) | environment where this infrastructure reside. | `string` | n/a | yes |
| <a name="input_product_domain"></a> [product\_domain](#input\_product\_domain) | product domain who owns this SSM Session Manager Configuration | `string` | n/a | yes |
| <a name="input_s3_bucket_description"></a> [s3\_bucket\_description](#input\_s3\_bucket\_description) | description for this bucket. | `string` | `"s3 bucket to store SSM session manager logs"` | no |
| <a name="input_s3_bucket_prefix"></a> [s3\_bucket\_prefix](#input\_s3\_bucket\_prefix) | (Optional) To write output to a sub-dir, enter a sub-dir name. | `string` | `""` | no |
| <a name="input_s3_enable_versioning"></a> [s3\_enable\_versioning](#input\_s3\_enable\_versioning) | Enable versioning for this bucket | `string` | `"true"` | no |
| <a name="input_s3_sse_algorithm"></a> [s3\_sse\_algorithm](#input\_s3\_sse\_algorithm) | Encryption algorithm used for this bucket | `string` | `"AES256"` | no |
| <a name="input_session_manager_document_name"></a> [session\_manager\_document\_name](#input\_session\_manager\_document\_name) | The name of SSM document for session manager, this default name is the one allowed by AWS | `string` | `"SSM-SessionManagerRunShell"` | no |
| <a name="input_ssm_document_description"></a> [ssm\_document\_description](#input\_ssm\_document\_description) | description for ssm document | `string` | `"document to hold regional session manager preferences"` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_iam_policy_arn"></a> [iam\_policy\_arn](#output\_iam\_policy\_arn) | the arn of iam policy for allowing session manager access |
| <a name="output_iam_policy_name"></a> [iam\_policy\_name](#output\_iam\_policy\_name) | the name of iam policy for allowing session manager access |
| <a name="output_s3_bucket_name"></a> [s3\_bucket\_name](#output\_s3\_bucket\_name) | the name of s3 bucket |
| <a name="output_ssm_document_name"></a> [ssm\_document\_name](#output\_ssm\_document\_name) | the name of ssm document for session manager preferences |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Contributing

This module accepting or open for any contributions from anyone, please see the [CONTRIBUTING.md](https://github.com/traveloka/terraform-aws-session-manager-config/blob/master/CONTRIBUTING.md) for more detail about how to contribute to this module.

## License

This module is under Apache License 2.0 - see the [LICENSE](https://github.com/traveloka/terraform-aws-session-manager-config/blob/master/LICENSE.md) file for details.
