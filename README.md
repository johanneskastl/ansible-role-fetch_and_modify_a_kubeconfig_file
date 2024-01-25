![Ansible Lint](https://github.com/johanneskastl/ansible-role-fetch_and_modify_a_kubeconfig_file/workflows/Ansible%20Lint/badge.svg)

# fetch_and_modify_a_kubeconfig_file

Fetch a kubeconfig file from e.g. a k3s or microk8s server and replace
`127.0.0.1` with an external IP address

## Requirements

None.

## Role Variables

- `local_file_name` (String): which filename to use for the fetched kubeconfig
  file (on the Ansible control node)
- `remote_file_path` (String): where to fetch the kubeconfig file from, i.e.
  the path on the remote machine
- `actual_IP_to_use` (String): which IP address (or variable) to use when
  replacing `127.0.0.1` in the kubeconfig file. If this variable is not set,
  the host's `ansible_default_ipv4` address will be used.

## Dependencies

None

## Example Playbook for k3s

```yaml
- hosts: servers
  roles:
    - role: 'johanneskastl.fetch_and_modify_a_kubeconfig_file'
      local_file_name: 'k3s-kubeconfig'
      remote_file_path: '/etc/rancher/k3s/k3s.yaml'
```

## Example Playbook for microk8s

```yaml
- hosts: microk8s-server
  roles:
    - role: 'johanneskastl.fetch_and_modify_a_kubeconfig_file'
      local_file_name: 'microk8s-kubeconfig'
      remote_file_path: '/var/snap/microk8s/current/credentials/client.config'
```

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via git@johannes-kastl.de
