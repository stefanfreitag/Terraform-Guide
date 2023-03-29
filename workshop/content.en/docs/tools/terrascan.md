+++
title = 'terrascan'
type = 'docs'
+++

## In one sentence

Terrascan is a static code analyzer for Infrastructure as Code.

## Installation

```shell
curl -L "$(curl -s https://api.github.com/repos/accurics/terrascan/releases/latest | grep -o -E "https://.+?_Linux_x86_64.tar.gz")" > terrascan.tar.gz
tar -xf terrascan.tar.gz terrascan && rm terrascan.tar.gz
sudo install terrascan /usr/local/bin && rm terrascan
```

## Usage

- Initialize _terrascan_. As part of this step policies from the Terrascan
GitHub repository are cloned to _~/.terrascan/pkg/policies/opa/rego_.

  ```shell
  terrascan init
  ```

- Scanning of Terraform files

  ```shell
  terrascan scan -i terraform
  ```

## Links

- [Github Repository](https://github.com/tenable/terrascan)
- [Documentation](https://runterrascan.io/docs/)
