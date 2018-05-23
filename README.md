docker-install role
=========
Downloads and installs:
- docker
- docker-compose

Also ensure the docker usergroup is created, and adds the user that is
executing the playbook to the docker group.

Role Variables
--------------
- docker_version: Version of docker to be installed
- docker_apt_key_url: Docker's gpg signing key
- docker_apt_key_fingerprint: Fingerprint to verifiy Docker's gpg key
- docker_apt_package: Name of docker package in apt
- docker_apt_dependencies: Required apt packages to install docker
- docker_repo: Docker repo to add to apt
- docker_version_ubuntu: Version of docker to be installed for ubuntu systems
- docker_comose_version: Version of docker-compose to be installed
- docker_compose_package_url: Url to download docker-compose
- docker_compose_path: Where to place docker-compose on the host system

Example Playbook
----------------
At the playbook level:
	- hosts: servers
      roles:
         - docker-install

    - hosts: linux
      tasks:
        - include_role: docker-install

At the role level:
	- name install docker
	  include_role: docker-install

