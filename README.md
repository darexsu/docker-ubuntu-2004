# Doсkerfile: Ubuntu-20.04 for Molecule CI 

[![Build](https://github.com/darexsu/docker-ubuntu-2004/actions/workflows/main.yml/badge.svg)](https://github.com/darexsu/docker-ubuntu-2004/actions/workflows/main.yml)
[![Docker pulls](https://img.shields.io/docker/pulls/darexsu/molecule-ubuntu-2004.svg?maxAge=2592000)](https://hub.docker.com/r/darexsu/molecule-ubuntu-2004/)

Ubuntu-20.04 for Ansible Playbooks testing

### Example molecule.yml
```yaml
---
dependency:
  name: galaxy
driver:
  name: docker
platforms:
  - name: instance
    image: "darexsu/molecule-ubuntu-2004:latest"
    command: ${MOLECULE_DOCKER_COMMAND:-""}
    volumes:
      - /sys/fs/cgroup:/sys/fs/cgroup:ro
    privileged: true    
provisioner:
  name: ansible
  playbooks:
    converge: converge.yml
```
