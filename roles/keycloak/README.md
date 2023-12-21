Ansible role for Keycloak

### Features

- Installs Keycloak
- Installs a systemd service
- Creates an admin user


### Requirements

- The target host must have systemd installed (e.g. CentOS/RHEL 7+, Debian 8+, Ubuntu 15.04+)


### Instructions

1. Create a playbook that includes this role and define any variables as described below

1. After running the playbook, open the firewall as needed
    - Port 8080 for HTTP
    - Port 8443 for HTTPS

1. Navigate to the server, e.g. https://192.168.56.100:8443

1. Go to the *Administration Console* and log in using the admin username and password you set (see *Variables* below)


### Variables

- `keycloak_admin_password` (required)
    - Password for the admin user
- `keycloak_admin_username` (optional)
    - Username for the admin user
    - Default value: `admin`
- `keycloak_group` (optional)
    - Default value: `keycloak`
- `keycloak_home` (optional)
    - Default value: `/opt/keycloak`
- `keycloak_java_version` (optional)
    - Default value: see [defaults/main.yml](defaults/main.yml)
- `keycloak_user` (optional)
    - Default value: `keycloak`
- `keycloak_version` (optional)
    - Version of Keycloak to install
    - Default value: see [defaults/main.yml](defaults/main.yml)
- `proxy_env` (optional)
    - Proxy settings; see https://docs.ansible.com/ansible/latest/user_guide/playbooks_environment.html#setting-the-remote-environment
    - Default value: `{}`


### Sample playbook

    - hosts: keycloak-servers
      roles:
        - keycloak
      vars:
        keycloak_admin_password: "{{ vault_keycloak_admin_password }}"


### Documentation

See [docs](docs) for various post-install documentation
