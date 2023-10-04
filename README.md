![ansble](https://github.com/manojmanu276/Ansible-Playbooks/assets/102495616/6adb1910-3aac-4ec3-9123-cdd76d3686b6)

# Ansible
This repository contains few important ansible  playbooks required for software provisioning and configuration management

## What is Ansible

Ansible is an open source IT automation tool that automates provisioning, configuration management, application deployment, orchestration, and many other manual IT processes.

## Use Cases of Ansible
* Automation(Any system automation, Server, Database, configuration, start restart services)
* Change Management (Production server changes)
* Provisionning(Setup server from scratch or cloud provisioning)
* Orchestration(Large scale automation framework, can integrate with other tool like jenkins, docker)

## How Ansible connects to remote machines
![219846350-a0c53ac4-0b2f-4781-ac6c-a5dd512ea649](https://github.com/manojmanu276/Ansible-Playbooks/assets/102495616/d6d0b47e-c432-456f-b14a-5622a422cf17)

Control machine: A control machine is the central node in an Ansible infrastructure. It is used to manage all the other machines in the network.
Remote machine: A remote machine is any machine that is not the control machine. Remote machines are managed by the control machine using SSH.
Target machine: A target machine is a remote machine being provisioned or configured by Ansible.

## What is Ansible Playbook

Playbooks are the files where the Ansible code is written. Playbooks are written in YAML format. YAML means "Yet Another Markup Language,". It is basically a blueprint of automation tasks—which are complex IT actions executed with limited or no human involvement.

## What is Ansible Inventory

Inventory file defines the hosts and groups of hosts upon which commands, modules, and tasks in a playbook operate. The file can be in one of many formats depending on your Ansible environment and plugins. The default inventory located at /etc/ansible/hosts

## What is Ansible Config file

The file that governs the behavior of all interactions performed by the control node. In Ansible’s case that default configuration file is (ansible.cfg) located in /etc/ansible/ansible.cfg.

Ansible uses the python module, python script to connect to the target machine. It dumps the python script and execute there and return the output.

![219847528-a54c5417-127c-4e44-9762-72e4d1a33775](https://github.com/manojmanu276/Ansible-Playbooks/assets/102495616/f5cbc0b8-e3c3-4112-872b-1587979bf3da)

## Hands-On

* Launch an EC2 instance and install Ansible ( This is the control machine)
* Launch more EC2 instances to manage them
* Create a inventory file in your control machine in Project directory
* Don't give password instead give private key

## Hosts Entry in Inventory file
```
host_name ansible_host=private_addr ansible_user=ubuntu ansible_ssh_private_key_file=instance.pem 
```

## Ansible command to ping all the configured servers
```
ansible -i inventory -m ping all
or
ansible -i inventory -m ping *
```
## Ansible command to run playbook
```
ansible-playbook playbook-name
```

## Ansible command to perform dry run on the playbook without making any actual changes
```
ansible-playbook playbook-name --check
```

## Ansible command to list the hosts against which this playbook will be executed
```
ansible-playbook playbook-name --list-hosts
```
## Ansible command to list the tags used in the playbook
```
ansible-playbook  playbook-name --list-tags
```

## Ansible command to skip certain steps/tasks included in playbook
```
ansible-playbook playbook-name --skip-tags "tag1, tag3"
```
## Ansible command to list the core modules
```
ansible -doc -l
```
