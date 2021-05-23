Deploy NodeJS
=========

This role deploys NodeJS on Raspberry OS. Room-Assistant requires NodeJS to work, the instructions at [Installing Room Assistant](https://www.room-assistant.io/guide/quickstart-pi-zero-w.html#installing-room-assistant) were translated into this role.

Requirements
------------
Ansible >= 2.9 with ssh-public-key already copied to the Raspberry device;  
Raspberry with Raspberry OS installed.


Role Variables
--------------

Only the following variables are used and should not be changed. These are role variables.

| Variable | Type | Value | Description |
|-------- |----|------|-----|
| nodejs_url | String | https://gist.githubusercontent.com/mKeRix/88b7b81e9bca044f74de1dc51696efb2/raw/799a20bca44cc61d8f8ae93878f2f28af8365a69/getNodeLTS.sh | The URL of the NodeJS install script 
| nodejs_path | String | PATH="$PATH:/opt/nodejs/bin" | The path to write in `~/.profile`


Dependencies
------------

No Ansible collection or role dependeny is required to run this role.

Example Playbook
----------------

Example playbook and inventory is inside the `tests` folder of the role.

License
-------

GPLv3

Author Information
------------------

Juri Calleri  
https://github.com/Nihvel