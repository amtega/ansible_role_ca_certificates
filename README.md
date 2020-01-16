# Amtega ca_certificates role

This is an [Ansible](http://www.ansible.com) role to deploy CA certificates on the system.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`. The role setups the following facts:

- `ca_certificates_hostvars_certs`: list of certificates loaded from host vars.
- `ca_certificates_managed`: list of certificates managed by the role.

## Example Playbook

This is an example playbook:

``` yaml
---
- name: msyql_jdpc_connector role sample
  hosts: localhost
  roles:  
    - amtega.ca_certificates
  vars:
    ca_certificates:
      - alias: myca    
        description: My CA certificate     
        state: present                     
        priority: high                     
        pem: |                             
          -----BEGIN CERTIFICATE-----
          ...
          -----END CERTIFICATE-----
```

## Testing

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

Once you have docker, you can run the tests with the following commands:

```shell
$ cd amtega.ca_certificates/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) 2019 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Juan Antonio Valiño García.
