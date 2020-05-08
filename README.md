Role Name
=========

A role to configure an onion service from a provisioned openbsd httpd site. Goal is to let users navigate to the portal without exiting the tor network than providing anonymity for the server.

Requirements
------------

This was tested using AWS on a server where httpd was provisioned with a static site. Further security should be done depending on threat model. [This article from riseup](https://riseup.net/hi/security/network-security/tor/onionservices-best-practices) is a good start.

Role Variables
--------------

default/main.yml
- FQDN: the fully qualified domain name of the website to provision an onion for.
	+ used for the hidden service directory folder in `/home/ec2-user/{{ FQDN }}/hidden_service`
	+ used to route the onion to its' resource files (the static site)  in `htdocs/{{ FQDN }}`
	+ various block tagging

Example Playbook
----------------

an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: onionservice FQDN: www.example.org }

License
-------

BSD

Author Information
------------------
github.com/mhoulditch
