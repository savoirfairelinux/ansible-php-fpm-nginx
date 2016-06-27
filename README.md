# php-fpm-nginx

*Sets up a PHP project running behind php-fpm and nginx.*

See [default variables](defaults/main.yml) for details.

## Requirements

* Ansible 2.0+
* One of these target systems:
    * Debian jessie
    * Ubuntu 16.04
* Nginx installed. Recommended role: [ansible-nginx][ansible-nginx]

## Example

```
- role: php-fpm-nginx
  php_base_name: project_name
  php_domain_name: project_name.example.com
  php_site_root: /opt/project_name/www
  php_index_filename: index.php
```

[ansible-nginx]: https://github.com/savoirfairelinux/ansible-nginx
