# ansible-test
Ansible script test

# Usage
- Install blackbox
https://github.com/StackExchange/blackbox

- Decript the vault_pass file
- Run the ansible playbook

    ansible-playbook -i inventories/local configure.yml --vault-password-file=vault_pass
    