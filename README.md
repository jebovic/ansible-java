Java
====

[![Build Status](https://travis-ci.org/jebovic/ansible-java.svg?branch=master)](https://travis-ci.org/jebovic/ansible-java) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.java-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/java)

Install and configure java

This role is a part of my [OPS project](https://github.com/jebovic/ops), follow this link to see it in action. OPS provides a lot of stuff, like a vagrant file for development VMs, playbooks for roles orchestration, inventory files, examples for roles configuration, ansible configuration file, and many more.

Compatibility
-------------

Tested and approved on :

* Debian jessie (8+)
* Ubuntu Trusty (14.04 LTS)
* Ubuntu Xenial (16.04 LTS)

Role Variables
--------------

```yaml
# java install configuration
java_apt_repositories: []
java_packages:
  - "{% if (ansible_distribution == 'Ubuntu' and ansible_distribution_version | version_compare('15.10', '>=')) %}openjdk-8-jre{% else %}openjdk-7-jre{% endif %}"
java_home: no

```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: jebovic.java }
```

Example : config
----------------

```yaml
# Choose a custom apt repo
java_apt_repositories:
  - "{% if (ansible_distribution == 'Ubuntu') %}ppa:openjdk-r/ppa{% else %}deb http://http.debian.net/debian jessie-backports main{% endif %}"
# Install version you want (for example java 8)
java_packages:
  - openjdk-8-jre
```

Tags
----

* java_config : only update JAVA_HOME

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
