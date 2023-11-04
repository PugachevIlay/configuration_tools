# How to use Ansible Vault

*P.S To use Ansible Vault, make sure you have Ansible installed on your configuration server.*

Run your Ansible roles that depend on data in vault files using the command:

```commandline
ansible-playbook name_of_playbook.yaml --ask-vault-pass
```

If you prefer not to enter your Ansible Vault password every time you run your playbooks, you can set up the following:
Create a `.txt` file to store your password, for example, `~/.config/default/vault-pass.txt`. Then, set an environment
variable <span style="color: #FF4500;">But please! Do not push this file to your repository! </span>:

```commandline
export ANSIBLE_VAULT_PASSWORD_FILE=~/.config/default/vault-pass.txt
```

You can verify the variable's value with:

```commandline
echo $ANSIBLE_VAULT_PASSWORD_FILE
```

After these steps, your password will be automatically entered every time you run your playbooks.

## Plugin for IDE

You can also use the Ansible Vault plugin in your IDE for decryption, which is available under the
title  <span style="color: #87CEEB;"> **Ansible Vault Plugin** </span>:
at https://plugins.jetbrains.com/plugin/14278-ansible-vault-editor.

## CLI commands

View the content of your vault:

```commandline
ansible-vault view ~/ansible/vault/users/cfg_users.yaml
```

or, with a password prompt:

```commandline
ansible-vault view ~/ansible/vault/users/cfg_users.yaml --ask-vault-pass
```

Create a new vault file:

```commandline
ansible-vault create ~/ansible/vault/users/new_cred.yaml
```

or, with a password prompt:

```commandline
ansible-vault create ~/ansible/vault/users/new_cred.yaml --ask-vault-pass
```

Edit data within a vault file:

```commandline
ansible-vault edit ~/ansible/vault/users/new_cred.yaml
```

or, with a password prompt:

```commandline
ansible-vault edit ~/ansible/vault/users/new_cred.yaml --ask-vault-pass
```

