ansible-role-snowflake
=========

This Ansible role helps you run Snowflake, a censorship resistant pluggable transport to help people reach the Tor network.

Currently the role helps you run a Snowflake server, which is different than a Snowflake proxy https://gitlab.torproject.org/tpo/anti-censorship/pluggable-transports/snowflake/-/tree/main/server

If you want to run a Snowflake proxy with Ansible, please check out https://github.com/nvjacobo/snowflake

Requirements
------------

You need root privileges or sudo user to run this role.

Role Variables
--------------

Check `defaults/main.yml` for the full list of variables and their defaults.

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- name: Run the ansible-role-snowflake role and include custom vars
  remote_user: root
  hosts: '{{ target }}'
  vars_files:
    - vars/snowflake-servers.yml
  roles:
    - ansible-role-snowflake

  pre_tasks:

  - name: Remove the snowflake repo to grab it fresh
    ansible.builtin.shell: "rm -rf /home/snowflake"
```

License
-------

GPLv3

Author Information
------------------

Created by https://unredacted.org/

Credits
------------------

Some code was used from https://github.com/nvjacobo/snowflake