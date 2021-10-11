# ansible-2
This repository contains essential server setup for web production provisioning by ansible.

# How to use
1. Update ssh login item in `~/.ssh/config`, and append it in `hosts.ini`, under "aws" entry. There is an example:

```
tail ~/.ssh/config
```
```
Host tfm
	HostName 1.2.3.4
	User ubuntu
	IdentityFile ~/.ssh/YOUR_PRIVATE_PEM_FILE
	UserKnownHostsFile /dev/null
	StrictHostKeyChecking no
```
2. Setup credentials in `vars/secrets.yml`, the example is listed as `vars/secrets.yml.example`.

3. Execute the tasks you'd like to execute. The tasks are including:
- server setup (install packages);
- API deployment with docker private registry (AWS ECR);
- Database setup (postgresql);
- Database backup

# NOTE
About configure web server to point to API service, this is not specifically implemented, since may `docker run math_power` is enough. Note the docker image already declared to use port 3000.  Or maybe I misunderstood the requirement.

On that step maybe I need to introduce nginx here for port forwarding.
