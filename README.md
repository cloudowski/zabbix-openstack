# Monitoring OpenStack with Zabbix

This repository contains zabbix resources for monitoring OpenStack environment.

# Features
The following features are currently available:
  * Automatic endpoints discovery via keystone API
  * Endpoints monitoring with predefined triggers
  * Configuration using macros

# Installation
  * Install **python-keystoneclient** on you Zabbix server
  * Copy scripts from  **server/externalscripts/** to your Zabbix server to **ExternalScripts** location
  * Import **templates/Template_OpenStack_Services.xml** template into your Zabbix server
  * Add OpenStack controller host (the one with Keystone component) to Zabbix and link **Template OpenStack Services** template to it

# Configuration
Configure the following macros on the **controller host level** in Zabbix so that server could connect to keystone:
  * **{$OS_AUTHURL}** - OpenStack keystone auth url (*http://127.0.0.1:5000/v2.0* by default)
  * **{$OS_TENANT}** - OpenStack tenant name (*admin* by default)
  * **{$OS_USER}** - OpenStack user name (*admin* by default)
  * **{$OS_PASSWORD}** - OpenStack user password (*admin* by default)

# License
This project is licensed under Apache License 2.0

# Contribute
Feel free to test, break, experiment and contribute :-)
