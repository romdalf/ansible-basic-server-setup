# ansible-basic-server-setup

Currently, this Ansible plays configure the followings:
- roles/provision; role to provision a server at Hetzner (currently not sync - still testing - don't use!)
- roles/configure; role to hostname, hosts file, firewalld, fail2ban, add first admin user, add EPEL, and update the service
  - checking with distribution and major release to target the proper package management system
  - hosts.j2 can be modified to fit needs
  - jail.local.j2 can be modified to fit needs
- roles/ovirt; role to install ovirt engine on RHEL7 (currently not sync - still testing - don't use!)

## usage

| Provider | Working Roles | Inventory |
|:---------|:--------------|:----------|
| Hetzner  | provision     | use the group [hetzner] and [hetzner:vars] to 
|          | configuration | specify the IP(s) and the webservice credentials
|          | ~~ovirt~~     | see https://wiki.hetzner.de/index.php/Robot_Webservice
