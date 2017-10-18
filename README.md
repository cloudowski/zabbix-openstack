# Monitoring OpenStack with Zabbix

This repository contains Zabbix resources for monitoring OpenStack environment.

# Features
The following features are currently available:
  * Automatically discover (using API), add service endpoints and monitor their availability and performance 
  * Automatically discover (using API), add hypervisor hosts and monitor availability, performance and other metrics
  * Active monitoring of OpenStack nodes - connections are initiated by agents installed on nodes
  * Flexible configuration based on variables (Zabbix macros)

# Installation
  * Install **python-keystoneclient** and **python-novaclient** on you Zabbix server
  * Install Zabbix agents on your OpenStack nodes and define **ServerActive** with IP address of the Zabbix server 
  * Copy scripts from  **server/externalscripts/** to your Zabbix server to **ExternalScripts** location
  * Import templates from **templates/** into your Zabbix server
  * Add OpenStack controller host (the one with Keystone component) to Zabbix and link **Template OpenStack** or **Template OpenStack Identity V3**  template to it
  * Wait for Zabbix to add discovered hypervisor hosts and endpoints items (look for them in the controller host)

# Configuration
Configure the following macros on the **controller host level** in Zabbix so that server could connect to keystone:
  * **{$OS_AUTHURL}** - OpenStack keystone auth url (*http://127.0.0.1:5000/v2.0* by default)
  * **{$OS_TENANT}** - OpenStack tenant name (*admin* by default)
  * **{$OS_USER}** - OpenStack user name (*admin* by default)
  * **{$OS_PASSWORD}** - OpenStack user password (*admin* by default)
  * **{$OS_USER}** - OpenStack user name (*admin* by default)
  * **{$OS_PASSWORD}** - OpenStack user password (*admin* by default)
  * **{$OS_USER_DOMAIN_NAME}** - (only for Identity API v3) OpenStack User domain name (*Default* by default)
  * **{$OS_PROJECT_DOMAIN_NAME}}** - (only for Identity API v3) OpenStack User domain name (*Default* by default)


# License
This project is licensed under Apache License 2.0

# Contribute
Feel free to test, break, experiment and contribute :-)
