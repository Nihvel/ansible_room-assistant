# Room-Assistant


## requirements.yml - Install the collection
Create `ansible.cfg` at the root level of this project.  

    [defaults]
    collections_paths = ./collections/ansible_collections

Open a terminal in the project folder and type:

    mkdir -p ./collections/ansible_collections

Run the install command.  

    ansible-galaxy collection install -r requirements.yml -p ./collections/


## Vault
Instruction to set up the vault file are inside the vault file itself.   
Variables like mqtt user, password and mqtt server should be kept secret.


## Inventory
Check the `<role>/tests/inventory` to know more about how to create your own inventory file.   
This guide can help you: [Build Your Inventory](https://docs.ansible.com/ansible/latest/network/getting_started/first_inventory.html)

## Variables
Role variables are within the `Vars` folder.  
These variables should be kept as they are unless you know what you are doing and have read the Ansible code of this project.

User's or host variables are inside the `Default` folder, but this project uses `host_vars` and `group_vars` for storing variables. 

Place in `host_vars/<your-living-room-host>/config.yml`  

    host_alias: living-room
    bluetooth_detection: true

And in `group_vars/room_assistant/vars.yml`  

    bluetooth_mac_list:
    - <first device bluetooth mac address>
    - <second device bluetooth mac address>

## Deploy

    ansible-playbook -i inventory deploy_room_assistant.yml --ask-vault-pass
