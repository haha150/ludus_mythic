# Ansible Role: Mythic Teamserver ([Ludus](https://ludus.cloud))

An Ansible role that installs and spins up a Mythic Teamserver on a Debian or Ubuntu server. The role automatically installs a couple of Mythic agents but feel free to fork to add for your own use.

## Dependencies

None.

## Example Playbook

```yaml
- hosts: mythic_teamserver_host
  roles:
    - haha150.ludus_mythic_teamserver
```

## Example Ludus Range Config

```yaml
ludus:
  - vm_name: "{{ range_id }}-mythic-teamserver"
    hostname: "{{ range_id }}-mythic"
    template: ubuntu-24.04-x64-server-template
    vlan: 20
    ip_last_octet: 2
    ram_gb: 8
    cpus: 2
    linux: true
    testing:
      snapshot: false
      block_internet: false
    roles:
      - haha150.ludus_mythic
```

