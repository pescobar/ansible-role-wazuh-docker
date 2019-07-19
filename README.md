ansible-role-wazuh-docker
=========

Deploy the official Wazuh docker containers from https://github.com/wazuh/wazuh-docker

Role Variables
--------------
```
wazuh_docker_install_docker_daemon: true

# https://documentation.wazuh.com/current/docker/wazuh-container.html#increase-max-map-count-on-your-host-linux
wazuh_docker_max_map_count: 262144

# this is the tag from dockerhub
# https://hub.docker.com/r/wazuh/wazuh/tags
wazuh_docker_version: "3.9.2_7.1.1"
```

Dependencies
------------

[geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker)
[robertdebock.selinux](https://galaxy.ansible.com/robertdebock/selinux)

**the selinux role will reboot the host if selinux is enabled**

By default the docker-daemon is installed. Use variable `wazuh_docker_install_docker_daemon: false` if you don't
want to install the docker daemon

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: ansible-role-wazuh-docker }

Author Information
------------------

Pablo Escobar Lopez
