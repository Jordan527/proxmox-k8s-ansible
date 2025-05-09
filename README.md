# Configuration

## Proxmox Hosts
Add the Proxmox hosts to `inventory.ini`

## Project Directory
In `project/group_vars/all`, change the project path to `<project_dir>/project`

## Vault
- Create the global vault
- Run `openssl passwd -6` to hash the password

```ansible-vault create project/group_vars/all/vault```
```
default_user: <user>
default_pass: <hashed pass>
sudo_pass: <sudo pass>
```

- Create the pve connection vault

```ansible-vault create project/group_vars/pvenodes/vault```
```
api_user: <user@pam>
api_token_id: <token>
api_token_secret: <secret>
```

- In `project`, create `vault_password.txt` with the password used for your vaults
