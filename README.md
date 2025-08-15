hai this is raman iam practicing ansible collection. and also creating resource on aws.

**If You are Working Wsl It will Need some steps before you perform.
--------------------------------------------------------------------
prerequisites:
============
-  python3.
     -  pip.
     -  boto3.
-  amazon collection.

Reason:-
=======
>>python environment is system-managed by OS.
>>So pip install system-wide is blocked to avoid breaking the OS Python packages.

Step1:-Use a virtual environment (recommended).

>>This is the safest approach for development.

>>Create a new virtual environment:

        ** $python3 -m venv ~/myenv
        
Step2:-Activate it

        ** $source ~/myenv/bin/activate
        
Step3:-Upgrade pip inside the venv:

        ** $pip install --upgrade pip
        
Step4:-Install boto3

        ** $pip install boto3
        
Step5:-When done, deactivate:

Note:-when work is done deactivate.Before you don't deactivate

        ** $deactivate

Step6:- Install Amazon Collection

        ** $ansible-galaxy collection install amazon.aws --force
        
            > $ansible-galaxy collection list | grep amazon.aws
=====================================================================

Ansible-vault Creation:-
----------------------

What is Ansible-vault:-
*********************

>Ansible Vault uses AES-256 symmetric encryption (default) to protect sensitive data.

>Symmetric encryption → same password is used for both encryption and decryption.

>The password is not stored in the file — only used to generate the encryption key.

>The encrypted file is just text (YAML or JSON structure) but all values are unreadable until decrypted.

>When you run ansible-playbook with Vault files, Ansible decrypts in memory before execution.
 The plain-text secrets   are never written to disk (unless you intentionally decrypt).

Ansible-vault Life Cycle:-
-----------------------

1>Create New Encrypted File.

    ** $ansible-vault create group_vars/all/pass.yml
    
2>Edit an Encrypted File.

    ** $ansible-vault edit group_vars/all/pass.yml

3>View Contents.

    ** $ansible-vault view group_vars/all/pass.yml

4>Encrypt an Existing Plain-Text File.

    ** $ansible-vault encrypt secrets.yml

5>Decrypt a File Permanently.

    ** $ansible-vault decrypt secrets.yml

6>Change Vault Password.

    ** $ansible-vault rekey group_vars/all/pass.yml

7>Encrypt a Single String (Inline).

    ** $ansible-vault encrypt_string 'SuperSecretKey' --name 'ec2_secret_key'

8>Run Playbooks with Vault.

 **Prompt for Password**
 
    ** $ansible-playbook site.yml --ask-vault-pass

9>Use a Vault Password File (automation).

     ** ansible-playbook site.yml --vault-password-file ~/ansible/vault.pass

    




