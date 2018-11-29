# ansible-role-letsencrypt

## Install
```
ansible-galaxy install tseho.letsencrypt
```

## Usage
Add the role in your playbook and create the following variables:
```
  vars:
    letsencrypt_domains:
      - example.com
      - www.example.com
    letsencrypt_email: contact@example.com
  roles:
    - tseho.letsencrypt
```

See [defaults](defaults/main.yml) for other available options.

## Renewal

A cronjob is automatically installed for the renewal of the certificate.
You just need to add the following in your own nginx configuration:
```
server {
    // ...

    location /.well-known {
        root {{ letsencrypt_public_dir | default('/var/www/letsencrypt') }};
        allow all;
    }
}
```
