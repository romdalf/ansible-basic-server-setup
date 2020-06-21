# ansible-basic-server-setup

Currently, this Ansible plays configure the followings:

| role | purpose|
|:-----|:-------|
| provision | role to (re)provision an operating system on a given server
| configure | role to (re)configure hostname, hosts file, firewalld, fail2ban, add first admin user, add EPEL, and update the service
| ovirt     | role to (re)deploy ovirt engine on RPM based distribution

## usage

| provider | roles         | status  | missing feature |
|:---------|:--------------|:--------|:----------------|
| Hetzner  | provision     | 90% | last task is about checking installation status by waiting for port 22 to become alive but this is not working because of the way the provisioning is wokirng with a "rescue" mode
|          | configuration | 50% | the configuration is only working with RPM based distribution (with yum or dnf)
|          | ovirt         | 0%   | not yet started
