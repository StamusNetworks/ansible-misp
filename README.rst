=========================
Ansible playbook for MISP
=========================

Introduction
============

As state the title, this is a Ansible playbook to install the Malware Information Sharing Platform
(MISP). See https://github.com/MISP/MISP for more information on MISP.

Usage
=====

This is a single run playbook. It will convert a basic debian installation
to a running MISP server. The debian installation must have a sudo user
for example `ams` and you ssh key must have been pushed to that user.

Once you have that server, you can setup a MISP group in Ansible. You can
add something like that to your `hosts` file or simply create one with that
content ::

 [misp]

 misp1 ansible_ssh_host=192.168.1.25 ansible_ssh_user=ams

Then edit `group_vars/misp` to put the information you need in it.

Once done, you can run ::

 ansible-playbook -i hosts misp.yaml

Please note that this is a run once installation: if you rerun after having
done some work in MISP interface, you may loose all your config files.
