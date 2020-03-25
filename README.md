TASK
====

This tasks updates DUCKDNS with the current public IP

Requirements
------------

A working duckdns domain registration

Role Variables
--------------

```
duckdns_token: <token>
duckdns_domain: <domain>
```


The Domain does NOT contain the duckdns.org part.

Dependencies
------------

There are no known dependencies.

Example
-------

```
ansible-playbook duckdns.yml -e dockdns_token=abcdefghij123456 -e duckdns_domain=mydomain
```

License
-------

BSD

Author Information
------------------

Michael Bonetsmuller <michael.bonetsmuller@gmail.com>
