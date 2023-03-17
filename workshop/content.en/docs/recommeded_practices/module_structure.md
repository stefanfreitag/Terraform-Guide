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

## Common Files

- _.editorconfig_  
  
  ```plain
  # top-most EditorConfig file
  root = true
  
  [*.md]
  max_line_length = 0
  trim_trailing_whitespace = false

  [*.yaml]
  intent_style = space
  indent_size = 2

  [*.{tf,tfvars,tpl}]
  indent_size = 2
  indent_style = space
  ```

- _.gitignore_  
  Specifies intentionally untracked files to ignore.
  
  ```plain
  # See http://help.github.com/ignore-files/ for more about ignoring files.
  
  # Terraform
  .terraform.lock.hcl
  .terraform  
  ```

- _.gitattributes_  
  A `gitattributes` file is a simple text file that gives attributes to pathnames.

  ```plain
  ###############################################################################
  # Set default behavior to automatically normalize line endings.
  ###############################################################################
  * text=auto
  ###############################################################################
  # For the following file types, normalize line endings to LF on checking and
  # prevent conversion to CRLF when they are checked out (this is required in
  # order to prevent newline related issues)
  ###############################################################################
  *.*     text eol=lf
  *.go    text eol=lf
  *.yml   text eol=lf
  *.yaml  text eol=lf
  *.md    text eol=lf
  *.tf    text eol=lf
  LICENSE text eol=lf
  ```

## Links

- [editorconfig](https://editorconfig.org/)
- [gitignore](https://git-scm.com/docs/gitignore)
- [gitattributes](https://git-scm.com/docs/gitattributes)
