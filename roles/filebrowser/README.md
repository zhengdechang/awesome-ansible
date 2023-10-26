# Filebrowser

Role ton install [Filebrowser](https://github.com/filebrowser/filebrowser).

## Requirments

None

Windows services are not supported

## Variables

### Mandatory variables

| Variable name     | Description                                          |
| ----------------- | ---------------------------------------------------- |
| filebrowser_owner | Linux user that'll run Filbrowser                    |
| filebrowser_group | Linux group that run Filebrowser                     |
| filebrowser_root  | Path to your files that will be shown on Filebrowser |

### Optionnal variables

| Variable name           |         Default value         | Description                                                                                                   |
| ----------------------- | :---------------------------: | ------------------------------------------------------------------------------------------------------------- |
| filebrowser_install_dir |      `/opt/filebrowser`       | Where Filebrowser is installed                                                                                |
| filebrowser_listen      |          `"0.0.0.0"`          | Host address to listen, `0.0.0.0` for all adresses                                                            |
| filebrowser_port        |            `8173`             | Filebrowser host port                                                                                         |
| filebrowser_baseurl     |                               | Base URL to access Filebrowser                                                                                |
| filebrowser_cert        |                               | TLS certificate path                                                                                          |
| filebrowser_key         |                               | TLS key                                                                                                       |
| filebrowser_config      | `/opt/filebrowser/config.yml` | path to JSON or YAML file                                                                                     |
| filebrowser_database    |  `/opt/filebrowser/data.db`   | Bolt DB database path (will create subfolders)                                                                |
| filebrowser_log         |            `false`            | Log output                                                                                                    |
| filebrowser_noauth      |            `false`            | Use the noauth auther when using quick setup                                                                  |
| filebrowser_username    |            `admin`            | Username for the first user when using quick config                                                           |
| filebrowser_password    |       `$2a$12$vTy9...`        | BCrypt hashed password for the first user when using quick config (default is "admin" so change the password) |

## Dependencies

None

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- hosts: browser_server
  gather_facts: true
  become: true

  vars:
    filebrowser_owner: root
    filebrowser_group: root
    filebrowser_listen: "127.0.0.1"
    filebrowser_port: 8080
    filebrowser_root: /mnt/
  tasks:
    - import_role:
        name: "filebrowser"
```

## Author Information

I made this Ansible role because I wanted a lightweight file browser for my ARM NAS to do some operations on my files (if I move file between 2 NFS mounts using my desktop PC, there is a transfer between my PC and my NAS, that's why I want to avoid it wih Filebrowser).
