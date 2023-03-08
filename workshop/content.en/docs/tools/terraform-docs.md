+++
title = 'terraform-docs'
type = 'docs'
description = ''
+++

A tool to generate documentation for Terraform modules in output formats like Markdown.

## Installation

```shell
curl -Lo ./terraform-docs.tar.gz https://github.com/terraform-docs/terraform-docs/releases/download/v0.16.0/terraform-docs-v0.16.0-linux-amd64.tar.gz
tar -xzf terraform-docs.tar.gz
sudo chmod +x ./terraform-docs
sudo chown root: ./terraform-docs
sudo mv terraform-docs /usr/local/bin/terraform-docs
```

## Usage

### Stand alone

```shell
terraform-docs markdown table --output-file README.md --output-mode inject /path/to/module
```

## Links

- [Github repository](https://github.com/terraform-docs/terraform-docs/)
- [Documentation](https://terraform-docs.io/)
