# SonarQube Packer for AWS AMI

Packer Ansible script for provisioning a SonarQube AWS AMI.

Installs SonarQUbe version 7.4.

This project's Ansible was lifted from these `geerlingguy`'s Ansible roles:

- [geerlingguy/ansible-role-java][]
- [geerlingguy/ansible-role-mysql][]
- [geerlingguy/ansible-role-sonar][]

## Prerequisites

1. Install [HashiCorp Packer][].
1. Set AWS account key and secret. Do this in one of two ways:
   1. Use a tool like [aws-vault][].
   1. Export your IAM user's `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`.
1. Run `export AMI_USERS=YOU_AWS_ACCOUNT_ID` to grant your AWS account permission to use the AMI.

## Usage

```bash
packer build sonarqube.json
```

Use the AMI ID (printed in the output) when you create the SonarQube AWS EC2 instance.

## Testing

### Ansible

The Ansible is linted using Molecule. Molecule does much more than lint. To learn more, see [Testing Ansible roles with Molecule][].

### Packer

Packer file syntax of `sonarqube.json` is tested using Packer's `validate` command.

[aws-vault]: https://github.com/99designs/aws-vault
[geerlingguy/ansible-role-java]: https://github.com/geerlingguy/ansible-role-java
[geerlingguy/ansible-role-mysql]: https://github.com/geerlingguy/ansible-role-mysql
[geerlingguy/ansible-role-sonar]: https://github.com/geerlingguy/ansible-role-sonar
[hashicorp packer]: https://www.packer.io/
[testing ansible roles with molecule]: https://opensource.com/article/18/12/testing-ansible-roles-molecule
