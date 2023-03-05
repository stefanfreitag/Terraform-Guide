+++
title = 'tfswitch'
type = 'docs'
+++


The _tfswitch_ command line tool lets you switch between different versions of Terraform.
This is very useful when working on multiple projects.

## Installation

  ```shell
  $ curl -L https://raw.githubusercontent.com/warrensbox/terraform-switcher/release/install.sh | sudo bash

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  100  9159  100  9159    0     0  38162      0 --:--:-- --:--:-- --:--:-- 38162
  warrensbox/terraform-switcher info checking GitHub for latest tag
  warrensbox/terraform-switcher info found version: 0.12.1168 for 0.12.1168/linux/amd64
  warrensbox/terraform-switcher info installed /usr/local/bin/tfswitch
  ```

## Usage

After _tfswitch_  is installed you can select the Terraform version you would
  like to use. If it is not exisitng locally, _tfswitch_ will download it.

```shell
$ tfswitch 1.2.5
Installing terraform at /home/stefan/bin
Downloading to: /home/stefan/.terraform.versions
19897064 bytes downloaded
Switched terraform to version "1.2.5"  
```

If you do not specify the version _tfswitch_ presents a list

```shell
$ tfswitch
Use the arrow keys to navigate: ↓ ↑ → ← 
? Select Terraform version: 
  ▸ 1.2.5 *recent
    1.2.4 *recent
    1.3.8 *recent
    1.3.9
↓   1.3.7
 
```

## Links

- [Github repository](https://github.com/warrensbox/terraform-switcher)
- [Documentation](https://tfswitch.warrensbox.com/)
