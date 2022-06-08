# ansible-role-dm-crypt

Easy way to disk/swap encrypt

## Install

```shell
ansible-galaxy role install git+https://github.com/sergelogvinov/ansible-role-dm-crypt.git,main
```

## Usage

Generate the key and store it in /root/.dmpass
Create encrypted 1Gb disk /var/lib/disk.img

```yaml
- hosts: all
  vars:
    dm_crypt_key_file: /root/.dmpass
    dm_crypt_luks_files: [{ luks_name: disk, file: /var/lib/disk.img, size: 1G }]
  roles:
    - ansible-role-dm-crypt
```
