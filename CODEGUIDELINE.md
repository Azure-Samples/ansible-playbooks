## Sample playbook Coding Guideline

### Description
Pls add below information at beginning of your playbook.
```
# Description
# ===========
# Please provide description of thie playbook. 
# - what's the end to end scenario
#
# Prequisite
# ===========
# Plese list prequisite to use this playbook, for example
# - dependent ansible roles
# - dependent packages with specific version
# - dependent services/binaries, eg. git, Docker etc
#
# Parameters
# ==========
# Explain how to get parameter values for this playbook.
#
# Reference
# =========
# List reference information or document here. Eg. How to do environment setup for this playbook, eg. grant permission.
```

### Coding guideline
- Add all variables into `vars`. In tasks, use variables then. Goal is user just need to update `vars` part, then no need to change tasks itself.
- File naming convention: <ServiceName>_<Action>_<Properties>.yml
- Folder layout: if there're multiple sample playbooks for one service, eg. subnet, you could create a folder to hold all samples.