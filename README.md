Role Name
=========

Easy to use letsencrypt ansible role to create and renew SSL certificates.
Current version is tested and works on __Ubuntu 16.04__.
In future more platforms will be added.

Requirements
------------

If you use the default `letsencrypt_mode` for creating ssl certificates then you __MUST__ enable http path `/.well-known` in your vhost configuration to allow letsencrypt to verify the ownership of your domain. If you use `standalone` mode then you don't need any changes in your vhost configuration. For more information about modes see __Role Variables__ section.

* Nginx example:
```
    location ~ /.well-known {
        allow all;
    }
```


Role Variables
--------------

- `letsencrypt_mode` - the mode for creating ssl certificate. Default mode is `webroot` which does not require to interrupt the http service during ssl certificate creation. If you don't have any http services in you deployment you can switch to `standalone` mode.
- `letsencrypt_webroot_dir` - if you use `webroot` mode then you need to provide webroot directory to enable letsencrypt to verify domain ownership
- `letsencrypt_domain` - the domain for which the certificate will be obtained.
- `letsencrypt_email` - an email for receiving important announcements and notices.
- `letsencrypt_renewal_cron_dest` - the remote destination for renewal cron which renews all installed letsencrypt certificates
- `letsencrypt_production` - if `yes`, letsencrypt creates live certificate ready to use. Otherwise it creates staging certificate.

Dependencies
------------

NA

Example Playbook
----------------

```
- hosts: servers
  roles:
     - role: itsankoff.letsencrypt
       letsencrypt_domain: example.com
       letsencrypt_email: itsankoff@example.com
       letsencrypt_webroot_dir: "/var/www"
```


License
-------

BSD


Author Information
------------------

For more information please contact me:
* Email: itsankoff@gmail.com
* [Github](https://github.com/itsankoff)
