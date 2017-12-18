# ansible-role-docker
Role for creating/managing a Docker Swarm cluster

[![license](https://img.shields.io/github/license/petalmd/ansible-role-docker.svg)](https://github.com/petalmd/ansible-role-docker)

Tested only on CoreOS

## Installation
```
$ ansible-galaxy install petalmd.docker-swarm
```

## Getting started
```
---
- name: Docker Manager
  hosts: docker-manager
  gather_facts: True
  roles:
    - defunctzombie.coreos-bootstrap
    - { role: docker-swarm, step: boostrap-manager-steps }


- name: Docker Worker
  hosts: docker-worker
  roles:
    - defunctzombie.coreos-bootstrap
    - { role: docker-swarm, step: boostrap-worker-steps }

# Hosts group are created when boostrap-worker-steps and boostrap-manager-steps run
- name: Docker Manager boostrap
  hosts: docker-manager-boostrap
  roles:
    - { role: docker-swarm, step: manager-boostrap }


- name: Retreive the join token
  hosts: docker-manager-operational[0]
  roles:
    - { role: docker-swarm, step: retreive-join-token }

- name: Join - manager nodes
  hosts: docker-manager-boostrap:!docker-manager-operational
  roles:
    - { role: docker-swarm, step: join-manager-nodes }

- name: Docker Worker boostrap
  hosts: docker-worker-boostrap
  roles:
    - { role: docker-swarm, step: docker-worker-boostrap }

- name: Join - worker nodes
  hosts: docker-swarm-worker-bootstrap
  roles:
    - { role: docker-swarm, step: worker-bootstrap }

```

## Contributing
Contributions, questions, and comments are all welcomed and encouraged!

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Credits

- [Julien Maitrehenry](https://github.com/jmaitrehenry)
