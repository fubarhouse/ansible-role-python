# Ansible Role: Python

Installs/Updates Python and PIP packages via PyEnv on Debian/Ubuntu servers.

*Note*: This role has been rewritten with simplicity in mind, and now works supurbly. Should you need to reinstall the contents with ansible there are now controlling variables to enable or ignore specific tasks and a task to remove the program before reinstalling.

Given the current state of this role, it is unlikely I will need to revisit it in the future. Should you think of something either useful or cool to add, or if you find a bug, please log an issue.

## Requirements

This module makes full use of Ansible-based modules and does not have any dependencies.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

### Process controls

```
fubarhouse_python_install_pyenv: true
fubarhouse_python_install_python: true
fubarhouse_python_install_pypi: true
````

### development controls

````
pyenv_clean_install: false
````

### python version

````
python_version: "3.5.1"
````

### repository urls

````
repo_pyenv: "https://github.com/yyuu/pyenv.git"
repo_pyenv_updater: https://github.com/yyuu/pyenv-update.git
````

### paths

````
pyenv_location: "~/.pyenv"
pyenv_path_main: "bin"
pyenv_path_updater: "plugins/pyenv-update"
python_path: "usr/bin"
pypi_path: "versions/{{ python_version }}/bin"
````

### executables

````
pyenv_exec_main: "pyenv"
pyenv_exec_updater: "bin/pyenv-update"
python_exec: "/usr/bin/python"
pypi_exec: "pip"
````

### python modules

````
pypi_modules:
  - { name: "virtualenv" }
  - { name: "pyOpenSSL" }
  - { name: "ndg-httpsclient" }
  - { name: "pyasn1" }
```

## Dependencies

  none

## Example Playbook

```
  - { role: fubarhouse.python, when: '"python" in installed_extras' }
```

## Installation

  * Add "python" to the installed_extras variable in your config.yml file to use this role with the playbook example above.
  * Override pypi_modules variable in your config.yml to install a list of gems instead of the default value of that keyed array.
  * Update your python version as required. You ca change version using `pyenv global $VERSION`
  * This system will realias the global version of python only on initial install of pyenv - changing version must be requested by user.

## License

MIT / BSD

## Author Information

This role was created in 2015 by [Karl Hepworth](https://twitter.com/fubarhouse).
