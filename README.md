# Ansible Role: OhMyZsh

An Ansible role for installing and configuring OhMyZsh. 

## Ansible in Docker

Check out this repo/documentation for information on how to run ansible in docker.

- [Github Repo](https://github.com/andygodish/ansible-docker)
- [Wikijs Documentation](https://github.com/andygodish/wikijs-storage/blob/main/ansible/docker-container.md)

### Mac Installation

When installing on Mac via the ansible-in-docker container outlined above, you need to access an interactive terminal within the container and execute the playbook with a `-K` flag. When supplying an `ansible-playbook` command with the `-K` flag, the promt to enter your password only briefly displays and does not allow you to enter any input, causing the playbook to fail. 

```
docker run \                        
-v ${PWD}:/app \
-v ~/.ssh:/home/appuser/.ssh/ \
--rm -it ansible /bin/bash
```

From in the container, run `ansible-playbook main.yaml -K` and you will be properly prompted to enter your sudo password. 