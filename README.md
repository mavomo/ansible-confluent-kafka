## Ansible + Confluent Kafka + Zookeeper : Getting started

####  This is a learning space. Please do not use as-is for more serious purpose
The public IP's of my server are renewed all the time. I should be fine for me to write them here.

## Before running the playbook:
 1. Make sure all your remote host recognize your [Ansible Control Node](https://docs.ansible.com/ansible/latest/getting_started/index.html)

    If you need to login via ssh to your remote host, copy you RSA key to <b>each</b> Ansible Managed Node:
    > ssh-copy-id username@remote_host_ip

    > The command above will prompt you for the remote host's password, and then it will copy the public key to the remote host's file:
    >
    >  ~/.ssh/authorized_keys

 2. Set the hosts.yml file to match your managed nodes IP addresses
    To see the matching version in a .ini format, look at

    > /draft/hosts_inventory.ini

 3. Play the inventory and the playbook all-together
    Pay attention, I need a password and I took a shortcut here:
 > ansible-playbook -i hosts.yml install_kafka.yml configure_zookeepers.yml --extra-vars ansible_become_pass=your-password

4. Everything should work fine on all stage, you can log manually to any broker and type the command :
   >  kafka-topics --list --bootstrap-server localhost:9092

The command should return as a response:

     __confluent.support.metrics

### Where to go from there ?
- There is a Getting Started tutorial [here](https://developer.confluent.io/quickstart/kafka-local/?session_ref=https://duckduckgo.com/#4-create-a-topic)
- You can use any tool to want to have a humanly visualization version of your cluster
- ...

