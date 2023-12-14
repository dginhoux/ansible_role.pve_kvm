# ROLE dginhoux.pve_kvm



## DESCRIPTION

This ansible role manage pve kvm instances.<br />
Each kvm instances must be registered on "main list" (see vars sections).
<br /><br />
Actions possible are : create, delete, update, poweron, poweroff and clone.<br />
This role can be easily called for interact on just ONE instance and made ONE action. 

## REQUIREMENTS

#### SUPPORTED PLATFORMS

| Platform | Versions |
|----------|----------|
| Debian | all |



| Platform | Versions |
|----------|----------|
| Proxmox | 6, 7, 8 |



#### ANSIBLE VERSION

Ansible >= 2.13

#### DEPENDENCIES

None.



## INSTALLATION

#### ANSIBLE GALAXY

```shell
ansible-galaxy install dginhoux.pve_kvm
```
#### GIT

```shell
git clone https://github.com/dginhoux/ansible_role.pve dginhoux.pve_kvm
```


## USAGE

#### EXAMPLE PLAYBOOK CREATE ONLY ONE (vm1) KVM INSTANCE

```yaml
- hosts: localhost
  connection: local
  roles:
    - name: Create pve kvm
      ansible.builtin.include_role:
        name: dginhoux.pve_pve
  vars:
    pve_kvm_limit_list:
      - vm1
    pve_kvm_force_action: create
```

#### EXAMPLE PLAYBOOK POWERON ALL KVM INSTANCES

```yaml
- hosts: localhost
  connection: local
  roles:
    - name: Create pve kvm
      ansible.builtin.include_role:
        name: dginhoux.pve_pve
  vars:
    pve_kvm_force_action: poweron
```

#### EXAMPLE PLAYBOOK UPDATE ONLY ONE (vm2) KVM INSTANCE

```yaml
- hosts: localhost
  connection: local
  roles:
    - name: Create pve kvm
      ansible.builtin.include_role:
        name: dginhoux.pve_pve
  vars:
    pve_kvm_limit_list:
      - vm2
    pve_kvm_force_action: update
```



## VARIABLES

#### DEFAULT VARIABLES

Default variables defined in `defaults/main.yml` : READ THIS FILE



#### DEFAULT OS SPECIFIC VARIABLES

Those variables files are located in `vars/*.yml` are used to handle OS differences.<br />
One of theses is loaded dynamically during role runtime using the `include_vars` module and set OS specifics variable's.

`NOT USED BY THIS ROLE`

## AUTHOR

Dany GINHOUX - https://github.com/dginhoux<br />
Some parts are inspired from this existing role : https://github.com/UdelaRInterior/ansible-role-proxmox-create-kvm


## LICENSE

MIT
