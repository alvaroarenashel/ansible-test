# ansible-test
Ansible script test

# Usage
1. Install blackbox
- Follow the instructions in https://github.com/StackExchange/blackbox#installation-instructions
- Generate a GPG key https://docs.github.com/en/github/authenticating-to-github/generating-a-new-gpg-key
- Give your key to someone who can add you to the system
- Test with the blackbox-test-file.txt encryption/decryption

2. Decript the vault_pass file

    blackbox_edit_start vault_pass.gpg
    
3. Run the ansible playbook

    ansible-playbook -i inventories/local configure.yml --vault-password-file=vault_pass

4. Encrypt the file

    blackbox_edit_end vault_pass.gpg

# Notes
- Creating a random password

    LC_ALL=C tr -dc 'A-Za-z0-9!"#$%&'\''()*+,-./:;<=>?@[\]^_`{|}~' </dev/urandom | head -c 25 ; echo    

- Importing kbx formatted keys

	gpg --no-default-keyring --keyring .blackbox/pubring.kbx  --export -a | gpg --import

