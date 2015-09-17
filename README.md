# Ansible Role: Python

Installs/Updates Python and PIP packages via PyEnv on Debian/Ubuntu servers.

## Requirements

Requires `curl` to be installed on the server.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

** The system will expect a fail if these variables are wrong**
This role executes the applications directly using the path and these variables must evaluate correctly.
```
pyenv_location: "/home/vagrant/.pyenv/bin/pyenv"
python_location: "/usr/bin/python"
pip_location: "/home/vagrant/.pyenv/shims/pip"
```
```
```
python_version: "3.5.0"
```
```
python_modules:
  - { name: "virtualenv" }
  - { name: "pyOpenSSL" }
  - { name: "ndg-httpsclient" }
  - { name: "pyasn1" }
  - { name: "Django" }
```

## Dependencies

  none

## Example Playbook

```
  - { role: fubarhouse.python, when: '"python" in installed_extras' }
```

## Installation

  * Add "python" to the installed_extras variable in your config.yml file to use this role with the playbook example above.
  * Override python_modules variable in your config.yml to install a list of gems instead of the default value of that array.
  * Update your python version as required. You ca change version using `pyenv global $VERSION`
  * This system will realias the global version of python only on initial install of pyenv - changing version must be requested by user.

## License

MIT / BSD

## Author Information

This role was created in 2015 by [Karl Hepworth](https://twitter.com/fubarhouse).
