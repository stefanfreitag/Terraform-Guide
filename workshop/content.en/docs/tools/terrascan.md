+++
title = 'terrascan'
type = 'docs'
+++

## Installation

```shell
curl -L "$(curl -s https://api.github.com/repos/accurics/terrascan/releases/latest | grep -o -E "https://.+?_Linux_x86_64.tar.gz")" > terrascan.tar.gz
tar -xf terrascan.tar.gz terrascan && rm terrascan.tar.gz
sudo install terrascan /usr/local/bin && rm terrascan
```

## Usage

- Execution

  ```shell
  terrascan init
  terrascan scan
  ```

- Scanning of Terraform HCL2 files for AWS resources

  ```shell
  terrascan  scan -t aws
  ```
