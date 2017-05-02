# php-fpm-nginx

*Sets up a PHP project running behind php-fpm and nginx.*

See [default variables](defaults/main.yml) for details.

## Requirements

* Ansible 2.2+
* One of these target systems:
    * Debian jessie
    * Ubuntu 14.04
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

## Uninstall

This role supports uninstalling cleanly. If you run the role with `php_uninstall` to `yes`,
resources created by the role will be removed. This however, excludes system packages because we
want to avoid removing packages that another role might need.

## FastCGI Cache

You can enable FastCGI Cache by setting `php_fastcgi_cache_enabled` to `true`.
If you want to clear the cache, you need to call from the same machine this
corresponding URL : `http://[[php_base_name]].purge.cache.fastcgi.nginx.local/`

More information about caching features can be found in `defaults/main.yml`.


[ansible-nginx]: https://github.com/savoirfairelinux/ansible-nginx
