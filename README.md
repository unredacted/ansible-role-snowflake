ansible-role-snowflake
=========

This Ansible role helps you run Snowflake, a censorship resistant pluggable transport to help people reach the Tor network.

Currently the role helps you run a Snowflake server, which is different than a Snowflake proxy https://gitlab.torproject.org/tpo/anti-censorship/pluggable-transports/snowflake/-/tree/main/server

At the moment, running a Snowflake server doesn't do anything as Snowflake clients won't use it. Described more in https://gitlab.torproject.org/tpo/anti-censorship/pluggable-transports/snowflake/-/issues/40248

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