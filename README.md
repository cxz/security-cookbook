# Basic security for Ubuntu

This is a simple chef recipe to automate the standard lock down steps on a fresh Ubuntu install, these are:

- Install Fail2Ban
- Install UFW (Firewall)
- Install Unattended Upgrades
- Set the system to download updates daily
- Disable SSH Password auth
- Allow SSH traffic through the firewall
- Allow any pre defined traffic through the firewall

## Firewall

This recipe will look for a key firewall_allow in the node definition.
If it is defined it will expect it to be an array of hashes in the form:

{ip: an_ip_address, port; a_port}

For each rule, the specified ip address will be granted access to the
specified port on the current node.
