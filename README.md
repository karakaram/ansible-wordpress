# ansible-wordpress

## Requirement

- CentOS 7.4
- Python 3.6
- Ansible 2.4.2
    - passlib python module

## Usage

```
echo ${your vaults password} > ~/.ansible_vault_password
cp server.pem roles/nginx/files
cp server.key roles/nginx/files
cp dhparam.pem roles/nginx/files
ansible-playbook bootstrap.yml -i production
ansible-playbook site.yml -i production
```