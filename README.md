# Ansible Role: Terraform

An Ansible role that wraps the `community.general.terraform` module.

# Requirements

* `terraform`

# Role Variables

Available variables are described in the table below.

| Variable Name                    | Default Value | Required | Description                                                                    | Example            |
|:--------------------------------:|:-------------:|:--------:|:------------------------------------------------------------------------------:|:------------------:|
| `terraform_operation`            | `apply`       | No       | Action terraform should take. Valid options are `apply` or `destroy`           | `apply`            |
| `terraform_project_path`         | ''            | Yes      | Path where *.tf files live                                                     | `path/to/tf_files` |
| `terraform_check_destroy`        | `true`        | No       | Apply only when no resources are destroyed.                                    |                    |
| `terraform_force_init`           | `true`        | No       | Force `terraform init` when no state file can be found.                        |                    |
| `terraform_init_reconfigure`     | `false`       | No       | Force backend reconfiguration during `init`.                                   |                    |
| `terraform_lock`                 | `true`        | No       | Enable state file locking.                                                     |                    |
| `terraform_overwrite_init`       | `true`        | No       | Run `terraform init` even if state file exists.                                |                    |
| `terraform_purge_workspace`      | `false`       | No       | Only works with `terraform_operation = destroy`. Cleans up workspace state.    |                    |
| `terraform_workspace`            | `default`     | No       | The name of the workspace to work with.                                        |                    |
| `terraform_backend_config`       | ''            | No       | Group of key/value pairs to provide to the `-backend-config` argument.         |                    |
| `terraform_backend_config_files` | ''            | No       | Path to configuration files to provide to the `-backend-config` argument.      |                    |
| `terraform_binary_path`          | ''            | No       | Path to the `terraform` executable.                                            |                    |
| `terraform_lock_timeout`         | ''            | No       | How long to maintain the lock on the state file.                               |                    |
| `terraform_parellelism`          | ''            | No       | Restrict concurrent operations when terraform applies the plan.                |                    |
| `terraform_plan_file`            | ''            | No       | Path to the existing terraform plan file to apply.                             |                    |
| `terraform_plugin_paths`         | ''            | No       | List of paths containing Terraform plugin executable files.                    |                    |
| `terraform_state_file`           | ''            | No       | Path to an existing terraform state file to use when building plan.            |                    |
| `terraform_targets`              | ''            | No       | List of specific resources to target.                                          |                    |
| `terraform_variables`            | ''            | No       | Group of key/value pairs to override template variables or those in var files. |                    |
| `terraform_variables_files`      | ''            | No       | Path to variables files for terraform to fill into the configurations.         |                    |

# Dependencies

* `community.general.terraform`

# Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      roles:
         - role: pumphouse_p.terraform
           terraform_operation: apply
           terraform_project_path: ./tf/core_infrastructure

License
-------

GPL

Author Information
------------------

Devin Parrish ([GitHub](https://github.com/pumphouse-p))
