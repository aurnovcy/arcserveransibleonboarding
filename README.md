# Onboarding Hybrid Machines to Azure Arc-enabled Servers at scale with Ansible

You can onboard your Ansible-managed machines to Azure Arc-enabled servers at scale by using an Ansible playbook. 

Ansible Playbooks support scalable and reusable configuration of multiple machines. A playbook is composed of one or more ‘plays’ in an ordered list. The terms ‘playbook’ and ‘play’ are sports analogies. Each play executes part of the overall goal of the playbook, running one or more tasks. Each task calls an Ansible module.
Learn more: https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html#playbook-execution

When you execute Ansible through an ad hoc command or by running a playbook, you must choose which managed nodes or groups you want to execute against. Patterns let 
you run commands and playbooks against specific hosts and/or groups in your inventory. An Ansible pattern can refer to a single host, an IP address, an inventory group, a set of groups, or all hosts in your inventory. 
Learn more: https://docs.ansible.com/ansible/latest/user_guide/intro_patterns.html/ 

## Step 1: Create a Service Principal 

You will need a service principal with the Connected Machine Agent Onboarding role. Please save both the service principal id and secret, as both will be used for onboarding. 
Learn more: https://docs.microsoft.com/en-us/azure/azure-arc/servers/onboard-service-principal#create-a-service-principal-for-onboarding-at-scale

## Step 2: Download the Ansible Playbook

Download the correct Ansible Playbook for your environment and needs. We provide four playbooks for both Windows and Linux and for both public endpoint and proxy server connectivity methods. 

Save the Ansible Playbook as 'arc-server-onboard-playbook.yml'. 

## Step 3: Modify the Ansible Playbook

Modify the Ansible Playbook to include the following parameters as prompted:

- Service Principal ID
- Service Principal Secret
- Resource Group
- Subscription Group
- Tenant Id
- Tags (Optional)
- Proxy (Optional)
- Region 

Additionally, modify the target servers from webservers to your desired subset of servers. You can also apply a pattern in defining the scope of target servers. 

## Step 4: Run the Ansible Playbook

Run the command with the name of the playbook to onboard to Azure Arc:
ansible-playbook arc-server-onboard-playbook.yml -f 10

