# ansible-wordpress

## Requirement

- CentOS 7.4
- pyenv
- pipenv

## Usage

```
pyenv install
pipenv install
pipenv shell
echo ${your vaults password} > ~/.ansible_vault_password
cp server.pem roles/nginx/files
cp server.key roles/nginx/files
cp dhparam.pem roles/nginx/files
ansible-playbook bootstrap.yml -i production
ansible-playbook site.yml -i production
```
