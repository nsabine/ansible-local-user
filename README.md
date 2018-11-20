# ansible-local-user

Demo playbook for how to add user using custom credentials.

Requires a custom credential (https://www.ansible.com/blog/ansible-tower-feature-spotlight-custom-credentials) with the following config:

Input configuration
````
fields:
  - type: string
    id: username
    label: Username
  - secret: true
    type: string
    id: password
    label: Password
  - type: string
    id: sshkey
    label: Public SSH Key (Optional)
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
