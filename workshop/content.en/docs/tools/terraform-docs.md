+++
title = 'terraform-docs'
type = 'docs'
description = ''
+++


## In one sentence

A tool to generate documentation for Terraform modules in output formats like
[Markdown](https://en.wikipedia.org/wiki/Markdown "Markdown in Wikipedia").

## Installation

The latest version can be downloaded from the [Github releaes
page](https://github.com/terraform-docs/terraform-docs/releases "Github releases
of terraform-docs").

{{< tabs "uniqueid" >}}
{{< tab "Linux" >}}

```shell
curl -Lo ./terraform-docs.tar.gz https://github.com/terraform-docs/terraform-docs/releases/download/v0.16.0/terraform-docs-v0.16.0-linux-amd64.tar.gz
tar -xzf terraform-docs.tar.gz
sudo chmod +x ./terraform-docs
sudo chown root: ./terraform-docs
sudo mv terraform-docs /usr/local/bin/terraform-docs
```

{{< /tab >}}
{{< /tabs >}}

## Usage

_terraform-docs_ can be executed stand alone or integrated into other tools like [pre-commit](https://pre-commit.com/ "pre-commit Homepage").

### Stand alone

One of the common approaches is render the documenation as Markdown and add it
to the _README.md_ that exists in the top level directory of most project. For
those cases the command below can be used, only the path to the Terraform module
needs to be adjusted.

```shell
terraform-docs markdown table --output-file README.md --output-mode inject /path/to/module
```

If you would not like to pass the configuration on the CLI, create a file _.terraform-docs.yml_
in the root directory of the Terraform module.

```yaml
formatter: "markdown table"

output:
  file: README.md
  mode: inject

sort:
  enabled: true
  by: name
```

The configuration file is passed using the _-c_ when invoking _terraform-docs_.

```shell
terraform-docs -c .terraform-docs.yml
```

## Links

- [Github repository](https://github.com/terraform-docs/terraform-docs/)
- [Documentation](https://terraform-docs.io/)
