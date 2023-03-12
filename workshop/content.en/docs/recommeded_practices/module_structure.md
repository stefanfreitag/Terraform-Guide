+++
title = 'Module structure'
type = 'docs'
+++


When writing Terraform modules it is good to follow established standards.
Hashicorp publishes for the different Terraform versions a recommended
aka [standard module structure](https://developer.hashicorp.com/terraform/language/modules/develop/structure "Standard Module Structure").

Here a brief overview

- Root Module
- _examples/_
  - Contains examples of using the module.  
  - Each example should have a _README_ to explain the goal and usage of the example.
- _main.tf_
  - The primary entrypoint.
  - Simple module:  this may be where all the resources are created.
  - Complex module: resource creation may be split into multiple files but any nested module calls should be in the main file.
- _outputs.tf_
  - Declaration of outputs
- _variables.tf_
  - Declaration of variables
