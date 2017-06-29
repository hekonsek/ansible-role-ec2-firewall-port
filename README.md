Ansible Role - Fedora EC2 instance
=========

Ensures that AWS EC2 security group firewall has given port open.

## Requirements

Keep in mind that Ansible EC2 module requires you to have Boto installed: 

    sudo pip install -U boto

You can specify AWS credentials either in Boto file (for example `~/.boto`) or using environment variables:
    
    AWS_ACCESS_KEY_ID='yourKeyId' AWS_SECRET_ACCESS_KEY='yourSecretKey' ansible-playbook aws.yml

## Installation 

    ansible-galaxy install hekonsek.ec2-firewal-port,0.0

## Role variables

- `keyName` - name that should be assigned to the uploaded SSH public key 

## Example playbook

```
# Expose port 80 to the outside world
- hosts: localhost
  connection: local
  gather_facts: false
  roles:
    - { role: hekonsek.ec2-firewal-port,0.0, vars: {targetPort: 80} }
```

## License

Apache 2.0