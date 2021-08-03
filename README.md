installer_downloader
=========

This role will help to download the AAP installer as well as uploading it to Satellite.

Role Variables
--------------

This role requires the following variables.
offline_token
  - Acquire your token at https://access.redhat.com/management/api/  ( https://access.redhat.com/articles/3626371 )

Optional Variables
  - requires_satellite (Default: False) # When setting this variable to True, the variables below become mandatory
  - satellite_user
  - satellite_password
  - satellite_server
  - satellite_organization
  - satellite_repository
  - satellite_product
  - satellite_content_view_name

You may find and vars file example at installer_dowloader/templates/vars.yml.j2

Example Playbook
----------------

~~~
---
- name: Downloader for AAP installers
  hosts: localhost
  vars_files:
    - vars.yml
  roles:
    - installer_dowloader
~~~

License
-------

BSD

Author Information
------------------

Lucas Benedito (lbenedit@redhat.com)
