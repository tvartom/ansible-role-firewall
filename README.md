ansible-role-firewall
=====================

Setup firewalld for CentOS 7 as an Ansible-role.

Requirements
------------

CentOS 7

Role Variables
--------------

    firewall:
      services:
        - name: "dhcpv6-client"
          comment: "My optional comment"
        - name: "ssh"
        - name: "http"
        - name: "https"
      extra_ports:
        - port: 9999
          protocol: tcp
          comment: "My optional comment"
      forward_ports:
        - port: 80
          to_port: 8080
          protocol: tcp
          comment: "My service"

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      tasks:
         - include_role:
             name: tvartom.firewalld
           var:
             firewall:
                extra_ports: []
                  - port: 9999
                    protocol: tcp
                    comment: "My service"

           

License
-------

CC-BY-4.0

Author Information
------------------

tvartom
