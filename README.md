# ar_os_group_users
Ansible Role 

## Requirements
- oc command line is available
- Execution is made by user able to add users to groups (oc adm groups add-users) 


## Role Variables
The following details:
- the parameters that should be passed to the role (aka vars)
- the defaults that are held
- the secrets that should generally be sourced from an ansible vault.

### Parameters:
| Variable                     | Description                              | Default        |
| --------                     | -----------                              | -------        |
| ar_os_group_users_members    | List of members to ba added to the group | []             |
| ar_os_group_users_group_name | Name of the group                        | null (invalid) |


### Defaults
| Variable                     | Description                              | Default                                    |
| --------                     | -----------                              | -------                                    |
| ar_os_group_users_assertions | List of assertions made before execution | 'ar_os_group_users_group_name' is provided |

### Secrets
The following variables should be provided through an encrypted source:

## Dependencies
None

## Example Playbook

```
- hosts: localhost
  tasks:
    - name: Include ar_os_group_users for 'testgroup'
      include_role:
        name: ar_os_group_users
      vars:
        ar_os_group_users_group_name: 'testgroup'
        ar_os_group_users_members:
          - testuser
          - admin
        
```

## License

MIT / BSD

## Author Information

This role was created in 2020 by David Stewart (dstewart@redhat.com)
