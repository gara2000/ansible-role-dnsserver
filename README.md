DNSSERVER
=========

This role configures a local DNS server

Requirements
------------

The only prerequisite for this role is that the server provisioned should be an ubuntu server

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

This role requires 3 variables to be set:
- domain [default: test.net]: the domain name 
- dnsserver_ip [required]: the ip of the dns server you are currently configuring
- servers [default: empty list]: list of servers other than the dns server, each item of the list should have a `name` and `ip` parameters

Dependencies
------------

No dependencies

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      vars:
        domain: "my_domain.net"
        dnsserver_ip: "192.168.60.4"
        servers:
          - name: webserver
            ip: 192.168.60.5
          - name: database
            ip: 192.168.60.6
      roles:
         - dnsserver

License
-------

BSD
