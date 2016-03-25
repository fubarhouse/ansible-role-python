# Ansible Role: Python

  Installs/Updates Python and PIP packages via PyEnv on Debian/Ubuntu servers.

  *Note*: This role has been rewritten with simplicity in mind, and now works supurbly. Should you need to reinstall the contents with ansible there are now controlling variables to enable or ignore specific tasks and a task to remove the program before reinstalling.

  Given the current state of this role, it is unlikely I will need to revisit it in the future. Should you think of something either useful or cool to add, or if you find a bug, please log an issue.

## Requirements

  None.

## Role Variables

  Available variables are listed below, along with default values (see `defaults/main.yml`):

  ### Clean install
  ````
  fubarhouse_python.clean_install: false
  ````
  ### Process controls
  ````
  fubarhouse_python.install_pyenv: true
  fubarhouse_python.install_python: true
  fubarhouse_python.install_pypi: true
  ````
  ### Repositories
  ````
  fubarhouse_python.repo_pyenv: "https://github.com/yyuu/pyenv.git"
  fubarhouse_python.repo_pyenv_updater: https://github.com/yyuu/pyenv-update.git
  ````
  ### Install directories
  ````
  fubarhouse_python.main_dir: "~/.pyenv"
  ````
  ### Install paths
  ````
  fubarhouse_python.main_path: "bin"
  fubarhouse_python.updater_path: "plugins/pyenv-update"
  fubarhouse_python.python_path: "usr/bin"
  fubarhouse_python.pypi_path: "versions/{{ python_version }}/bin"
  ````
  ### Executables
  ````
  fubarhouse_python.main_exec: "pyenv"
  fubarhouse_python.updater_exec: "bin/pyenv-update"
  fubarhouse_python.python_exec: "/usr/bin/python"
  fubarhouse_python.pypi_exec: "pip"
  ````
  ### Application versions
  ````
  fubarhouse_python.python_version: "3.5.1"
  ````
  ### Packages
  ````
  fubarhouse_python.packages:
    - { name: "virtualenv" }
    - { name: "pyasn1" }
  ````

## Dependencies

  None.

## Example Playbook

  ```
    - { role: fubarhouse.python, when: '"python" in installed_extras' }
  ```

## Installation

  * Add "python" to the installed_extras variable in your config.yml file to use this role with the playbook example above.
  * Override fubarhouse_python.packages variable with the above structure in your config.yml to install a list of gems instead of the default value of that keyed array.
  * Update your python version as required. You can change version using `pyenv global $VERSION`
  * This system will realias the global version of python only on initial install of pyenv - changing version must be requested by user.

## License

  MIT / BSD

## Author Information

  This role was created in 2015 by [Karl Hepworth](https://twitter.com/fubarhouse).

  This role was redeveloped in 2015 by [Karl Hepworth](https://twitter.com/fubarhouse).
