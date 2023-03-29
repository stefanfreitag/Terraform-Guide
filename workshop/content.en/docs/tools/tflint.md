+++
title = 'tflint'
type = 'docs'
+++

## In one sentence

_tflint_ is a pluggable Terraform linter.

Finds possible errors (like invalid instance types) for Major Cloud providers
(AWS/Azure/GCP). Warn about deprecated syntax, unused declarations. Enforce best
practices, naming conventions.

## Installation

- Use the provided installation script

{{< tabs "uniqueid" >}}
{{< tab "Linux" >}}

```shell
$ curl -s https://raw.githubusercontent.com/terraform-linters/tflint/master/install_linux.sh | bash
arch=amd64
os=linux_amd64


====================================================
Looking up the latest version ...
Downloading TFLint v0.45.0
Downloaded successfully


====================================================
Unpacking /tmp/tflint.b2bXR2dwTh/tflint.zip ...
Archive:  /tmp/tflint.b2bXR2dwTh/tflint.zip
  inflating: /tmp/tflint.b2bXR2dwTh/tflint
Installing /tmp/tflint.b2bXR2dwTh/tflint to /usr/local/bin/ ...
'/tmp/tflint.b2bXR2dwTh/tflint' -> '/usr/local/bin/tflint'
Cleaning temporary downloaded files directory /tmp/tflint.b2bXR2dwTh ...


====================================================
Current tflint version
TFLint version 0.45.0
+ ruleset.terraform (0.2.2-bundled)
```

{{< /tab >}}
{{< /tabs >}}

## Usage

- Create a configuration file _.tflint.hcl_
- For using the recommended presets add
  
  ```hcl
  plugin "terraform" {
    enabled = true
    preset  = "recommended"
  }
  ```
  
  The recommended checks are
  
  |Rule|Description|Recommended|
  | --- | --- | --- |
  |terraform_comment_syntax|Disallow `//` comments in favor of `#`||
  |terraform_deprecated_index|Disallow legacy dot index syntax|✔|
  |terraform_deprecated_interpolation|Disallow deprecated (0.11-style) interpolation|✔|
  |terraform_documented_outputs|Disallow `output` declarations without description||
  |terraform_documented_variables|Disallow `variable` declarations without description||
  |terraform_empty_list_equality|Disallow comparisons with `[]` when checking if a collection is empty|✔|
  |terraform_module_pinned_source|Disallow specifying a git or mercurial repository as a module source without pinning to a version|✔|
  |terraform_module_version|Checks that Terraform modules sourced from a registry specify a version|✔|
  |terraform_naming_convention|Enforces naming conventions for resources, data sources, etc||
  |terraform_required_providers|Require that all providers have version constraints through required_providers|✔|
  |terraform_required_version|Disallow `terraform` declarations without require_version|✔|
  |terraform_standard_module_structure|Ensure that a module complies with the Terraform Standard Module Structure||
  |terraform_typed_variables|Disallow `variable` declarations without type|✔|
  |terraform_unused_declarations|Disallow variables, data sources, and locals that are declared but never used|✔|
  |terraform_unused_required_providers|Check that all `required_providers` are used in the module||
  |terraform_workspace_remote|`terraform.workspace` should not be used with a "remote" backend with remote execution|✔|
  
([Source](https://raw.githubusercontent.com/terraform-linters/tflint-ruleset-terraform/v0.2.0/docs/rules/README.md))

- The AWS plugin can be added in similar manner to _.tflint.hcl_.

  ```hcl
  plugin "aws" {
    enabled = true
    version = "0.22.1"
    source  = "github.com/terraform-linters/tflint-ruleset-aws"
  }
  ```

## Links

- [Github repository](https://github.com/terraform-linters/tflint)
- [Terraform Ruleset](https://github.com/terraform-linters/tflint-ruleset-terraform)
- [AWS Ruleset](https://github.com/terraform-linters/tflint-ruleset-aws)
