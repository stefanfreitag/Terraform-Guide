+++
title = 'tfsec'
type = 'docs'
+++

_tfsec_ is a static code analyzer provided by [Aqua Security](https://www.aquasec.com/).

## Installation

- Download using the provided _install.sh_ script

  ```shell
  curl -s https://raw.githubusercontent.com/aquasecurity/tfsec/master/scripts/install_linux.sh | bash
  ```

- Checking the installed _tfsec_ version
  
  ```shell
  $ tfsec --version
  v1.28.1
  ```
  
## Usage

- From the command line execute

  ```shell
  $ tfsec
  timings
  ──────────────────────────────────────────
  disk i/o             43.624µs
  parsing              4.783863ms
  adaptation           93.453µs
  checks               2.397983ms
  total                7.318923ms

  counts
  ──────────────────────────────────────────
  modules downloaded   0
  modules processed    1
  blocks processed     30
  files read           6

  results
  ──────────────────────────────────────────
  passed               5
  ignored              0
  critical             0
  high                 0
  medium               0
  low                  0


  No problems detected!
  ```

### Configuration file

The _tfsec_ config file is a file in the _.tfsec_ folder in the root check path
named _config.yml_ and is automatically loaded if it exists.

A very basic configuration file is shown below

```yaml
---
minimum_severity: LOW
```

## Links

- [Github repository](https://github.com/aquasecurity/tfsec)
- [Documentation](https://aquasecurity.github.io/tfsec/)
