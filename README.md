# Ansible Playbooks for Azure

This repository contains examples and best practices for building Ansible Playbooks for Azure. 

## Getting Started

[Ansible on Azure](TBD)

[Get Started with Azure](http://docs.ansible.com/ansible/latest/guide_azure.html)

[Ansible Playbook](http://docs.ansible.com/ansible/latest/playbooks.html)

### Prerequisites

Azure Account. If you don't have it, get a [free one](https://azure.microsoft.com/en-us/free/).

To authenticate with Azure, generate [service principal](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal) and expose them as environment variables or store them as a file. 

### Quickstart
To run samples in your local environment, please ensure [Ansible](http://docs.ansible.com/ansible/latest/intro_installation.html) is installed. 

    1. git clone https://github.com/Azure-Samples/ansible-playbooks.git
    2. cd ansible-playbooks
    3. ansible-playbook <sample>.yml

You also could develop your Ansible playbook and run it in [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=vscoss.vscode-ansible).

## Resources

See [Ansible Galaxy](http://galaxy.ansible.com) for example roles from the Ansible community for deploying many popular applications. 
