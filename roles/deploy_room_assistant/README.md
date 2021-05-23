Deploy Room-Assistant
=========

This role deploys Room Assistant on Raspberry OS. Room-Assistant requires NodeJS to work, make sure you have checked the role `deploy_nodejs`

Requirements
------------
Ansible >= 2.9 with ssh-public-key already copied to the Raspberry device;  
Raspberry with Raspberry OS installed.


Role Variables
--------------

**host_vars**

| Variable | Type | Value | Description |
|-------- |----|------|-----|
| host_alias | String | living-room | The name of the host as Alias. Used to give a name to each member of the room-assistant |
| bluetooth_detection | Bool | true\|false | Set to true if room-assistance should deploy the presence detection role

**group_vars**

If `bluetooth_detection` is true, make sure to update the variable `bluetooth_mac_list` with a list of the bluetooth devices to track.

| Variable | Type | Value | Description |
|-------- |----|------|-----|
| bluetooth_mac_list | List | 00:00:00:00:00:00 | List of the bluetooth devices MAC address to monitor


Dependencies
------------

This role depends on the `community.general` Assible collection and `deploy_nodejs` role included in this same project.  

How to install the collection:  
Create `ansible.cfg` at the root level of this project.  

    [defaults]
    collections_paths = ./collections/ansible_collections

Open a terminal in the project folder and type:

    mkdir -p ./collections/ansible_collections

Used the file at the top level of this repository or create one copying this whole command: 

    cat << EOF > requirements.yml
    collections:
      - community.general
    EOF

Run the install command.  

    ansible-galaxy collection install -r requirements.yml -p ./collections/

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