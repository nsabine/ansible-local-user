# ansible-local-user

Demo playbook for how to add user using custom credentials.

Requires a custom credential (https://www.ansible.com/blog/ansible-tower-feature-spotlight-custom-credentials) with the following config:

Input configuration
````
fields:
  - type: string
    id: username
    label: Custom username
  - secret: true
    type: string
    id: password
    label: Custom password
  - type: string
    id: sshkey
    label: Custom Public SSH Key (Optional)
required:
  - username
  - password
````

Injector Configuration
````
extra_vars:
  custom_user_name: '{{ username }}'
  custom_user_password: '{{ password }}'
  custom_user_ssh_key: '{{ sshkey }}'
````
