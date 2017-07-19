Winlogbeat
=========

This role installs and configures Winlobeat service.

Requirements
------------

This roles needs to be run agains a Windows machine - of course - and requires the presence of [Chocolatey](https://chocolatey.org/). A [role](https://github.com/stone-payments/ansible-choco) to install choco can be used. 

Role Variables
--------------

```yaml
winlogbeat_installation_path: 'C:\\ProgramData\\chocolatey\\lib\\winlogbeat\\tools\\winlogbeat-5.4.0-windows-x86_64\\winlogbeat.yml'

use_elasticsearch: false
```
These vars are to be given on your playbook:

```yaml
logstash_endpoint: ''
logstash_port: ''

elasticsearch_endpoint: ''
elasticsearch_port: ''
```
Use the logstash ones to configure the output to logstash and the elasticsearch ones to output to elasticsearch.

Example Playbook
----------------
Here is an example setting the output to logstash:

    - hosts: servers
      roles:
         - role: ansible-winlogbeat
           logstash_endpoint: your.logstash.endpoint
           logstash_port: 42

Here is an example setting the output to elasticsearch:

    - hosts: servers
      roles:
         - role: ansible-winlogbeat
           elasticsearch_endpoint: your.elasticsearch.endpoint
           elasticsearch_port: 42

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
