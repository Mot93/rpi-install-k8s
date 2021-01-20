Role Name
=========

A role design to install k8s on a cluser of raspberry pis

Requirements
------------

The community.general.modprobe plugin is necessary for the role.

    ansible-galaxy collection install community.general

You need root privileges to run this script.

    become: yes

Role Variables
--------------

Currently, there are 2 container runtime to choose from: docker and containerd.
To choose the container runtime to use, set the variable `container_runtime` to one of the avaliable option.

Example:

    ansible-playbook example.yml --extra-vars "container_runtime=comntainerd"

For more information: [defining variable at runtime](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#defining-variables-at-runtime)

Dependencies
------------

To use this role, fist all requirement have to be met.

Use the requirement.yml file to automate the process of downloading all the requirement.

    ansible-galaxy install -r requirements.yml

Example Playbook
----------------

Installing the play

    ansible-galaxy install git+https://github.com/Mot93/rpi-install-k8s.git

Out of the box example:

    - hosts: dramble
      remote_user: ubuntu
      become: yes
      roles:
        - rpi-install-k8s

Example choosing the container runtime among the avaliable:

    - hosts: dramble
      remote_user: ubuntu
      become: yes
      roles:
        - role: rpi-install-k8s
          vars:
            container_runtime: containerd

License
-------

MIT

Author Information
------------------

If you like my work and whant to know more, visit my website:
[mattiarubini.com](https://mattiarubini.com)
