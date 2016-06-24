# Ansible Role: Python

[![Build Status](https://travis-ci.org/fubarhouse/fubarhouse.python.svg?branch=master)](https://travis-ci.org/fubarhouse/fubarhouse.python)

* PyEnv on Darwin/Debian/RedHat servers.
* Installs multiple python versions as required.
* Sets a global default python version to use
* Installs PIP packages

## Requirements

  None.

## Role Variables

Default Python version

    python_version: 2.7.11

All Python versions to install

    python_versions:
      - 2.7.11
      - 3.5.1

Python packages to download

    python_packages:
      - pyyaml
      - jinja2
      - virtualenv
      - pyasn1
      - Django

## Dependencies

  None.

## Example Playbook

    - { role: fubarhouse.python }

## Installation

* Add the Python role to your playbook.
* Modify above variables as desired.

## License

MIT / BSD

## Author Information

This role was created in 2015 by [Karl Hepworth](https://twitter.com/fubarhouse).
