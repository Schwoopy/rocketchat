Rocketchat and ansible
=========

A small ansible role that creates a pod with a nextcloud instance.

Requirements
------------

This role uses a community.crypto module to generate a self signed certificate.

Role Variables
--------------

    rocketchat_http_port: "8080"
    rocketchat_https_port: "8443"
    rocketchat_cert_cn: "YourServername.local"
    rocketchat_cert_ou: "Your Org"
    rocketchat_container_read_only: false
    rocketchat_container_remove_container: true

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: "Create a Rocketchatt env"
      hosts: "localhost"
      become: false
      gather_facts: true
      vars:
        rocketchat_container_remove_container: "false"
        rocketchat_container_read_only: "true"
      tasks:
        - name: "Install, configure and deploy a Rocketchat container with pods"
          import_role:
            name: "role-container-rocketchat"


License
-------

Apache License 2.0

Author Information
------------------

Schwoopy 2022
