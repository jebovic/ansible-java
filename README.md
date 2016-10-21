Java
====

[![Build Status](https://travis-ci.org/jebovic/ansible-java.svg?branch=master)](https://travis-ci.org/jebovic/ansible-java) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.java-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/java)

Install and configure java

Role Variables
--------------

```
# java install configuration
java_packages:
  - "{% if (ansible_distribution == 'Ubuntu' and ansible_distribution_version | version_compare('15.10', '>=')) %}openjdk-8-jre{% else %}openjdk-7-jre{% endif %}"
java_home: no
```

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - { role: jebovic.java }
```

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
