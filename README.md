# Onboarding Hybrid Machines to Azure Arc-enabled Servers at scale with Ansible

Ansible Playbooks support scalable and reusable configuration of multiple machines. A playbook is composed of one or more ‘plays’ in an ordered list. The terms ‘playbook’
and ‘play’ are sports analogies. Each play executes part of the overall goal of the playbook, running one or more tasks. Each task calls an Ansible module.
Learn more: https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html#playbook-execution

When you execute Ansible through an ad hoc command or by running a playbook, you must choose which managed nodes or groups you want to execute against. Patterns let 
you run commands and playbooks against specific hosts and/or groups in your inventory. An Ansible pattern can refer to a single host, an IP address, an inventory group, 
a set of groups, or all hosts in your inventory. 
Learn more: https://docs.ansible.com/ansible/latest/user_guide/intro_patterns.html/ 

## Step 1: Create a Service Principal with the Connected Machine Agent Onboarding Role

## Step 2: Download the Ansible Playbook

Download the correct Ansible Playbook for your environment and needs. We provide four playbooks for Windows and Linux in both public endpoint and proxy server 
connectivity methods.

## Step 3: Modify the Ansible Playbook

Modify the Ansible Playbook to include service principal id, service principal secret, resource group, subscription group, and tenant id.

Additionally, modify the target servers from webservers to your desired subset of servers by using a pattern. 

## Step 4: Run the Ansible Playbook

Run the command with the name of the playbook to onboard to Azure Arc:

ansible-playbook arc-server-onboard-playbook.yml -f 10
