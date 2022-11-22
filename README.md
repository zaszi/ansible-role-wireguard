# Ansible Role: Wireguard

Deploys both client and server configurations for [Wireguard](https://www.wireguard.com/).

## Requirements

To install Arch Linux packages, this role relies on the pacman module of the community general collection. Install it with `ansible-galaxy collection install community.general`.

This role requires `systemd-networkd` to be installed on both client and server hosts.

## Role Variables

| Variable    | Choices/**Default**      | Comments                                                                                                  |
| ----------- | ------------------------ | --------------------------------------------------------------------------------------------------------- |
| arch        | **auto**, armv7h, armv8h | Machine architecture, defaults to `auto` for x86_64, but must be changed for ARM-based machines           |
| wg_server   | **hostname**, …          | The name of the server. If this equals the current machine hostname, it installs the server configuration |
| wg_endpoint | **example.com**, …       | The domain for the host. Note that this must be unique per machine                                        |
| wg_address4 | **10.200.200.1**, …      | The IPv4 address for the host. Note that this must be unique per machine                                  |
| wg_address6 | **10.200.200.1**, …      | The IPv6 address for the host. Note that this must be unique per machine                                  |

## Dependencies

None.

## Example Playbook

    - hosts: all
      become: true
      roles:
         - ansible-role-wireguard

## License

Ansible-role-wireguard is licensed under the [MIT license](LICENSE).
