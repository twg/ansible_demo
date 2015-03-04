# Ansible Demo

Simple IT automation. http://ansible.com

## Setup

#### Ansible

The easiest way to install Ansible on OSX is using Homebrew.

```bash
brew install ansible
```

#### Vagrant and VirtualBox

Follow the instructions in the [Vagrant demo](https://github.com/twg/vagrant_demo) to get Vagrant and VirtualBox on your machine.

#### Vagrant Commands

- **vagrant up [*name*]**

    Create and provision all VMs or a named one

- **vagrant destroy [*name*]**

    Destroy all VMs or a named one

- **vagrant ssh *name***

    SSH into the VM specified by *name*

- **vagrant provision [*name*]**

    Re-provision all VMs or a named one

## [001_playbooks](001_playbooks)

1. Uncomment the `001_playbooks` section in [Vagrantfile](Vagrantfile).
2. Create and provision the VMs using `vagrant up`.
3. Peruse the [Playbook](001_playbooks/playbook.yml).

## [002_inventory](002_inventory)

1. Destroy the VMs
2. Uncomment the `002_inventory` section.
3. Create and provision the VMs using `vagrant up`.
4. Inspect the [Inventory](002_inventory/development).

## [003_roles](003_roles)

1. Uncomment the `003_roles` section.
2. Re-provision the VMs.
3. Read the [Roles](003_roles/roles).

## [004_variables](004_variables)

1. Uncomment the `004_variables` section.
2. Re-provision the VMs
3. View the [Variables](004_variables/group_vars)

## [005_targetting](005_targetting)

1. Uncomment each of the numbered sections under `005_variables`.
2. Re-provision the VMs for each section.  Each section documents the equivalent `ansible-playbook` command to achieve the same result against a remote server.
3. Try the [Tags](005_targetting/app-servers.yml)

## Resources

- Ansible Docs - http://docs.ansible.com/

    Documentation for all things Ansible.

- Ansible Galaxy - https://galaxy.ansible.com/

    Repository for reusable Ansible roles.

- Ansible Provisioner - http://docs.vagrantup.com/v2/provisioning/ansible.html

    Using Ansible as a provsioner for Vagrant.
