#ansible_pass_lookup
====================
An Ansible lookup for [password store](https://www.passwordstore.org/) passwords 

This lookup enables the ansible admin to retrieve, create or update passwords from
his pass store. It also retrieves YAML style keys stored as multilines in the passwordfile

Examples
--------
(for detailed information see [ansible website](http://docs.ansible.com/ansible/playbooks_lookups.html)

Basic lookup. Fails if example/test doesn't exist
`password="{{ lookup('pass', 'example/test'}}`

Create pass with random 16 char password. If password exists just give the password
`password="{{ lookup('pass', 'example/test create=true'}}`

Different size password
`password="{{ lookup('pass', 'example/test create=true length=42'}}`

Create pass and overwrite the password if it exists
As a bonus, this module includes the old password inside the pass file
`password="{{ lookup('pass', 'example/test create=true overwrite=true'}}`

Return the value for user in the KV pair user: username
`password="{{ lookup('pass', 'example/test subkey=user'}}`

Return the entire pass file content
`password="{{ lookup('pass', 'example/test returnall=true'}}`
