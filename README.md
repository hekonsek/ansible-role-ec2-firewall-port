# Ansible role - Fedora EC2 instance

Ensures that AWS EC2 security group firewall has given port open.

## Requirements

Keep in mind that Ansible EC2 module requires you to have Boto installed: 

    sudo pip install -U boto

You can specify AWS credentials either in Boto file (for example `~/.boto`) or using environment variables:
    
    AWS_ACCESS_KEY_ID='yourKeyId' AWS_SECRET_ACCESS_KEY='yourSecretKey' ansible-playbook aws.yml

## Installation 

    ansible-galaxy install hekonsek.ec2-firewal-port,0.2

## Role variables

- `region` - AWS region to use. Default region is `us-east-1` i.e. the cheapest one.
- `group` - name of the security group to create and use. Default value is `default`.

## Example playbook

```
# Expose port 80 to the outside world
- hosts: localhost
  connection: local
  gather_facts: false
  roles:
    - { role: hekonsek.ec2-firewal-port,0.2, vars: {targetPort: 80} }
```

## License

Apache 2.0