# ansible-basic-server-setup

Currently, this Ansible plays configure the followings:
- provision.yml; role to provision a server at Hetzner (currently not sync - still in test)
- configure.yml; role to  hostname, hosts file, firewalld, fail2ban, add first admin user, add EPEL, and update the service
- ovirt.yml; role to install ovirt engine on RHEL7

