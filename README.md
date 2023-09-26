# Ansible
This repository contains few important ansible  playbooks required for software provisioning and configuration management

## Ansible command to run playbook
ansible-playbook playbook-name 

## Ansible command to perform dry run on the playbook without making any actual changes
ansible-playbook playbook-name --check

## Ansible command to list the hosts against which this playbook will be executed
ansible-playbook playbook-name --list-hosts

## Ansible command to list the tags used in the playbook
ansible-playbook  playbook-name --list-tags

## Ansible command to skip certain steps/tasks included in playbook
ansible-playbook playbook-name --skip-tags "tag1, tag3" 
