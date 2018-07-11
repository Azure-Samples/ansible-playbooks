[![Travis CI](https://travis-ci.org/Azure-Samples/ansible-playbooks.svg?branch=full-ci)](https://travis-ci.org/Azure-Samples/ansible-playbooks)

## Full CI
This branch `full-ci` will run all sample playbooks in this repo, regularly. Current frequency is weekly.

## CI plan for ansible-playbooks repo
[ansible-playbooks](https://github.com/Azure-Samples/ansible-playbooks.git) CI plan as below

|Trigger|frequency|CI Coverage|.travis.yml branch|
|--|--|--|--|
|PR|per PR|Only run updated playbook yaml files|[master](https://github.com/Azure-Samples/ansible-playbooks/blob/master/.travis.yml)|
|Scheduled Job| Weekly| Run all sample playbook yaml files|[full-ci](https://github.com/Azure-Samples/ansible-playbooks/blob/full-ci/.travis.yml)|

### Excluced playbook lists
Some playbooks cannot be run in CI environment, for example [vm_create_existingvnet_deployjavaapp.yml](https://github.com/Azure-Samples/ansible-playbooks/blob/master/vm_create_existingvnet_deployjavaapp.yml), this playbook will create a VM with private IP, then access it. This playbook is not runnable in CI environment due to private IP. To exclude a playbook in CI, updated `.travis.yml` at both [master](https://github.com/Azure-Samples/ansible-playbooks/blob/master/.travis.yml) branch and [full-ci](https://github.com/Azure-Samples/ansible-playbooks/blob/full-ci/.travis.yml) branch, add it to list [excludedList](https://github.com/Azure-Samples/ansible-playbooks/blob/master/.travis.yml#L55).

### Run playbooks in subfolder with specific orders
Some playbooks need be executed in specific order, for example `vmss-create.yml`, `vmss-scale-out.yml` under `vmss` folder.  To run playbooks in specific oder, update `.travis.yml` at both [master](https://github.com/Azure-Samples/ansible-playbooks/blob/master/.travis.yml) branch and [full-ci](https://github.com/Azure-Samples/ansible-playbooks/blob/full-ci/.travis.yml) branch, follow sample [here](https://github.com/Azure-Samples/ansible-playbooks/blob/full-ci/.travis.yml#L81-L83).
