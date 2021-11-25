## Role Name: Nginx

Ansible role which allows you to install Nginx on Debian systems.

## Requirements

None.

## Role Variables

Nginx prerequisites.
````yaml
nginx_prerequisites: [gnupg2, ca-certificates, debian-archive-keyring"]
````

Nginx apt key id.
````yaml
nginx_apt_key_id: 573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62
````

Nginx apt keyring path.
````yaml
nginx_apt_keyring_path: /usr/share/keyrings/nginx-archive-keyring.gpg
````

Nginx apt key.
````yaml
nginx_apt_key_url: https://nginx.org/keys/nginx_signing.key
````

# You can switch to mainline nginx packages
nginx_apt_repo_url: "deb [signed-by={{ nginx_apt_keyring_path }}] http://nginx.org/packages/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} nginx/"


## Dependencies

None.

## Example Playbook

````yaml
    - hosts: all
      become: yes
      roles:
         - ansible-role-nginx
````

## License

MIT / BSD

## Author Information

Role created by Piotr Kurylak.
