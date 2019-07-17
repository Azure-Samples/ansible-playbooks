---
page_type: sample
languages:
- yaml
products:
- azure
description: "Examples and best practices for building Ansible Playbooks for Azure"
---

[![Travis CI](https://travis-ci.org/Azure-Samples/ansible-playbooks.svg?branch=full-ci)](https://travis-ci.org/Azure-Samples/ansible-playbooks)

# Ansible Playbooks for Azure

This repository contains examples and best practices for building Ansible Playbooks for Azure.

## Prerequisites

- Azure Account. If you don't have one, get a [free one](https://azure.microsoft.com/en-us/free/).

  To authenticate with Azure, generate [service principal](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal) and expose them as environment variables or store them as a file.

- Install [Ansible](http://docs.ansible.com/ansible/latest/intro_installation.html)
- Install Azure dependencies package

  ```sh
  pip install ansible[azure]
  ```

- Install [azure_preview_modules](https://galaxy.ansible.com/Azure/azure_preview_modules/) role.
- Install azure_preview_module role's dependencies packages.

  ```sh
  pip install -r ~/.ansible/roles/azure.azure_preview_modules/files/requirements-azure.txt
  ```

## How to run

To run samples in your local environment,

- `git clone https://github.com/Azure-Samples/ansible-playbooks.git`
- `cd ansible-playbooks`
- modify playbook to replace variables with yours, such as resource group name.
- [add Azure credential info](http://docs.ansible.com/ansible/latest/scenario_guides/guide_azure.html) by using one of the following options.

First option, set the following environment variables:

```ini
AZURE_CLIENT_ID=<service_principal_client_id>
AZURE_SECRET=<service_principal_password>
AZURE_SUBSCRIPTION_ID=<azure_subscription_id>
AZURE_TENANT=<azure_tenant_id>
```

Second option, add the following content to the file `$HOME/.azure/credentials`:

```ini
[default]
subscription_id=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
client_id=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
secret=xxxxxxxxxxxxxxxxx
tenant=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Third option, do a az login:

```sh
az login
```

- `ansible-playbook sample.yml`

You also could develop your Ansible playbook and run it in [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=vscoss.vscode-ansible).

### Using Azure cloud shell in Visual Studio Code

Azure cloud shell automatically logs you in your azure subscription so you need not to do anything extra other than login to cluod shell and run the ansible-playbook command with -e switch to provide
resource_group_name variable value. 

To be able to run Cloud Shell in Visual Studio Code, you will need to install [Azure Account Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.azure-account) in VS Code.

After installing the Azure Account extension, Login to cloud shell in VS code and clone this repository. Upload the Ansible Playbook you want to run to cloud drive and run the following command (replace `yourusernameincloudshell` with your username value). Make sure you also replace the `playbook name` and corrosponding `variable name` expected by playbook.

```ansible
ansible-playbook /home/yourusernameincloudshell/create_virtualmachine_with_subnet_in_different_resource_group.yml -e "resource_group_name=ansible_test_rg"
```

## How to Contribute

Please refer to [Coding Guideline](./CODEGUIDELINE.md) on how to contribute.

## Resources

[Ansible on Azure](https://docs.microsoft.com/en-us/azure/ansible/ansible-overview)

[Get Started with Azure](http://docs.ansible.com/ansible/latest/guide_azure.html)

[Ansible Playbook](http://docs.ansible.com/ansible/latest/playbooks.html)

[Ansible role azure_preview_modules](https://galaxy.ansible.com/Azure/azure_preview_modules/)

[Ansible Galaxy](http://galaxy.ansible.com) for example roles from the Ansible community for deploying many popular applications. 

## License

[MIT License](./LICENSE.md)

This project welcomes contributions and suggestions.  Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us the rights to use your contribution. For details, visit https://cla.microsoft.com.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Test
Sample playbooks in this repository are tested via travis CI, please see detail [CI plan](https://github.com/Azure-Samples/ansible-playbooks/blob/full-ci/README.md).
