## Purpose
<!-- Describe the intention of the changes being proposed. What problem does it solve or functionality does it add? -->
* ...

## Does this introduce a breaking change?
<!-- Mark one with an "x". -->
- [ ] Yes
- [ ] No

## Pull Request Type
What kind of change does this Pull Request introduce?

<!-- Please check the one that applies to this PR using "x". -->
- [ ] Bugfix
- [ ] Feature
- [ ] Code style update (formatting, local variables)
- [ ] Refactoring (no functional changes, no api changes)
- [ ] Documentation content changes
- [ ] Other... Please describe:

## How to Test
*  Install ansible

```bash
$ pip install ansible[azure]
```

*  [Optional] Install ansible role

```bash
$ ansible-galaxy install azure.azure_preview_modules
$ pip install -r ~/.ansible/roles/azure.azure_preview_modules/files/requirements-azure.txt
```

*  Get the sample playbook

```
git clone https://github.com/Azure-Samples/ansible-playbooks.git
cd ansible-playbooks
git checkout [branch-name]
```

* Test the code
<!-- Add steps to run the tests suite and/or manually test -->
```bash
ansible-playbook <filename>.yml
```

## What to Check
Verify that the playbook is successfully run.

## Other Information
<!-- Add any other helpful information that may be needed here. -->
