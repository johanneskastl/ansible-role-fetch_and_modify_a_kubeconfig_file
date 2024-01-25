![Ansible Lint](https://github.com/johanneskastl/ansible-role-fetch_and_modify_a_kubeconfig_file/workflows/Ansible%20Lint/badge.svg)

# fetch_and_modify_a_kubeconfig_file

Fetch a kubeconfig file from e.g. a k3s or microk8s server and replace
`127.0.0.1` with an external IP address

## Requirements

None.

## Role Variables

None.

## Dependencies

None

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: 'johanneskastl.fetch_and_modify_a_kubeconfig_file'
```

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via git@johannes-kastl.de
