Ansible role for podman pod
===========================

This role helps install and configure a podman POD.

Requirements
------------

- **OS Platforms:** RHEL 8/9, Debian, Ubuntu 22.04+
- **Dependent Roles:**
  - `podman` (declared in `meta/main.yml`)

Role Variables
--------------

| Variable Name | Default Value | Description |
| :--- | :--- | :--- |
| `podman_pod_user` | `podman_pod` | The user account name where the POD will be running from. |
| `podman_pod_group` | `podman_pod` | The group account name where the POD will be running from. |
| `podman_pod_shell` | `/bin/bash` | The user account shell to connect to. |
| `podman_pod_name` | `podman_pod` | The POD name. |
| `podman_pod_network` | `reverse-net.network` | The bridge network name to run the POD on. |
| `podman_pod_allow_unprivileged_ports` | `True` | Defines if unprivileged ports is allowed or not. |
| `podman_pod_published_ports` | `[8080:80, 8443:443]` | The list of published POD ports to the host machine. |


Example Playbook
----------------

```yaml
- name: Deploy podman_pod
  hosts: servers
  become: true
  roles:
    - role: lxtnow.podman_pod
      vars:
        podman_pod_name: steamer
```

License
-------

MIT


Author Information
------------------

- **Owner:** lxtnow
