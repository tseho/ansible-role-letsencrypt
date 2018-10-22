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
