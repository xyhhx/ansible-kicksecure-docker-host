<div align="center">

# Kicksecure Docker Host Playbook

Canonical Source: https://git.sr.ht/~xyhhx/ansible-kicksecure-docker-host

Mirrors:
[Github](https://github.com/xyhhx/ansible-kicksecure-docker-host) | [Codeberg](https://codeberg.org/xyhhx/ansible-kicksecure-docker-host)

</div>

Use these playbooks to configure a Debian server to be distro-morphed to [Kicksecure](https://kicksecure.org), hardened a bit more, and configured to run Docker.

This playbook was tested using OVH servers with an SSH key preinstalled (on the `debian` user instead of `root`)

## Usage

### Prerequisites

You need a Linux (or Unix) system with only a few things preinstalled:

- [GNU Make](https://www.gnu.org/software/make/)
- [Ansible](https://www.ansible.com)

### Set up 

1. I generate a random word for my privileged user's username (security through obscurity bla bla bla)
1. I generate an Ed25519 SSH key
1. Set up the environment vars like so:

    ```sh
    cp .env.example .env
    # Fill out the env vars
    $EDITOR .env
    ```

1. Finally, install the required Ansible Galaxy collections

    ```sh
    make install-requirements
    ```


### Running the playbooks 

Just run the following commands and it should just set everything up for ya 

```sh
make a setup-user
make up
```
