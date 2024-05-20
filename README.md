DNSSERVER
=========

This role configures a local DNS server

Requirements
------------

The only prerequisite for this role is that the server provisioned should be an ubuntu server

Role Variables
--------------

This role requires 3 variables to be set:
- domain [default: test.net]: the domain name 
- dnsserver_ip [required]: the ip of the dns server you are currently configuring
- servers [default: empty list]: list of servers other than the dns server, each item of the list should have a `name` and `ip` parameters

Dependencies
------------

No dependencies

Example Playbook
----------------

```bash
- hosts: servers
  become: yes
  vars:
    domain: "my_domain.net"
    dnsserver_ip: "192.168.60.4"
    servers:
      - name: webserver
        ip: 192.168.60.5
      - name: database
        ip: 192.168.60.6
  roles:
      - gara2000.dnsserver
```

License
-------

BSD
