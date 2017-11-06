Role Name
=========

Super easy to use ansible letsencrypt role to obtain an certificate with `certonly` option.
Current version is tested and works on __Ubuntu 16.04__. In future more platforms will be added.

Requirements
------------

No process to listen on port :80 on the destination machine. In future version
script will automatically handle this case.

Role Variables
--------------

`{{ letsencrypt_domain }}` - the domain for which the certificate will be obtained.  
`{{ letsencrypt_email }}` - an email for receiving important announcements and notices.

Dependencies
------------


Example Playbook
----------------

```
- hosts: servers
  roles:
     - role: itsankoff.letsencrypt
       letsencrypt_domain: example.com
       letsencrypt_email: itsankoff@example.com
```


License
-------

BSD

Author Information
------------------

For more information please contact me:
* Email: itsankoff@gmail.com
* [Github](https://github.com/itsankoff)
