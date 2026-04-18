asterisk-role-frp
=========

A simple role for installing [frp](https://github.com/fatedier/frp).

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: Install frp.
      hosts: servers
      gather_facts: true

      vars:
        frp:
          install_type: client
          client:
            server:
              url: frp.example.kz
              port: 7000
            tls:
              enabled: true
              certificate: "client.crt"
              privkey: "client.key"
              cacrt: "ca.crt"
            proxies:
              - name: my-homeassistant-tcp
                type: tcp
                localIP: 192.168.1.2
                localPort: 8123
                remotePort: 8123
            visitors: []
      roles:
         - frp

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
