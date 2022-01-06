installer_downloader
=========

This role will help to download the AAP installer as well as uploading it to Satellite.


Requirements
--------------
[redhat.satellite](https://console.redhat.com/ansible/automation-hub/repo/published/redhat/satellite)

Role Variables
--------------
This role requires the following variables.
  - offline_token
    - Acquire your token at https://access.redhat.com/management/api/  ( https://access.redhat.com/articles/3626371 )

Optional Variables
  - requires_satellite **(Default: False)**
    - When setting this variable to True, the variables below become mandatory
  - satellite_user
  - satellite_password
  - satellite_server
  - satellite_validate_certs **(Default: False)**
  - satellite_organization
  - satellite_repository
  - satellite_product
  - satellite_content_view_name

You can find a vars file example at [installer_dowloader/templates/vars.yml.j2](https://github.com/lucas-benedito/installer_dowloader/blob/master/templates/vars.yml.j2).

Example Playbook
----------------
~~~
---
- name: Downloader for AAP installers
  hosts: localhost
  vars_files:
    - vars.yml
  roles:
    - { role: lucas_benedito.installer_downloader }
~~~

Note
----------------
In case you wish to change the downloaded version, set the variable aap_version in vars.yml with the desired repository name.

E.g.:
AAP 2.0 E.A
~~~
aap_version: ansible-automation-platform-2.0-early-access-for-rhel-8-x86_64-files
~~~

AAP 2.1
~~~
aap_version: ansible-automation-platform-2.1-for-rhel-8-x86_64-files
~~~

To find the repo name, you may verfy it with the following command as registered system:
~~~
subscription-manager repos |grep ansible-automation-platform
~~~

License
-------
MIT / BSD

Author Information
------------------
Lucas Benedito (lbenedit@redhat.com)
