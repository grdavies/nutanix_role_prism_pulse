# Nutanix Role to configure Pulse on either Prism Element or Prism Central

This Ansible role downloads and deploys Nutanix Prism Central.


## Role Variables

| Variable                                          | Required | Default | Choices                   | Comments                                                                                |
|---------------------------------------------------|----------|---------|---------------------------|-----------------------------------------------------------------------------------------|
| nutanix_host                                      | yes      |         |                           | The IP address or FQDN for the Prism (Element or Central) to which you want to connect. |
| nutanix_username                                  | yes      |         |                           | A valid username with appropriate rights to access the Nutanix API.                     |
| nutanix_password                                  | yes      |         |                           | A valid password for the supplied username.                                             |
| nutanix_port                                      | no       | 9440    |                           | The Prism TCP port.                                                                     |
| validate_certs                                    | no       | no      | yes / no                  | Whether to check if Prism UI certificates are valid.                                    |
| nutanix_debug                                     | no       | False   | True / False              | Whether to output variable contents for debugging purposes.                             |
| nutanix_deploy_pc_pulse                           | no       | True    | True / False              | True enables pulse. False disables pulse                                                |
| nutanix_pulse_enable_default_nutanix_email        | no       | False   | True / False              |
| nutanix_pulse_email_contact_list                  | no       | []      |                           |
| nutanix_pulse_identification_info_scrubbing_level | no       | "AUTO"  |                           |
| nutanix_pulse_is_pulse_prompt_needed              | no       | False   | True / False              |
| nutanix_pulse_nos_version                         | no       | null    |                           |
| nutanix_pulse_remind_later                        | no       | False   | True / False              |


## Dependencies

- grdavies.nutanix_role_prism_init_api


## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
    - role: grdavies.nutanix_role_prism_central_deploy
  vars:
    nutanix_host: 10.38.185.37
    nutanix_username: admin
    nutanix_password: nx2Tech165!
    nutanix_pulse_status: True
```


## License

See LICENSE.md

## Author Information

Ross Davies
