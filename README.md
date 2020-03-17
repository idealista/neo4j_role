![Logo](https://raw.githubusercontent.com/idealista/neo4j_role/master/logo.gif)

[![Build Status](https://travis-ci.org/idealista/neo4j_role.png)](https://travis-ci.org/idealista/neo4j_role)

# Neo4j Ansible role

This Ansible role installs a Neo4j graph database **community** version in a Debian environment.

- [Getting Started](#getting-started)
  - [Prerequisities](#prerequisities)
  - [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)
- [Built With](#built-with)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Contributing](#contributing)
- [Acknowledgments](#acknowledgments)

## Getting Started

These instructions will get you a copy of the role for your ansible playbook. Once launched, it will install a [Neo4j graph database](https://neo4j.com/) in a Debian system.

Upgrade major versions is not supported with this role.

Due to modifications in the properties of the different major versions, the role version may only works with the version setted in the `neo4j_version` default parameter.

### Prerequisities

Ansible 2.8.6 version installed.
Inventory destination should be a Debian environment.

Java must be installed to run the service. Check [System requirements](https://neo4j.com/docs/operations-manual/current/installation/requirements/) to see supported versions. Java can be installed using the [Idealista's Java Ansible role](https://github.com/idealista/java-role).

For testing purposes, [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver.

### Installing

Create or add to your roles dependency file (e.g requirements.yml) from GitHub:

```yml
- src: http://github.com/idealista/neo4j_role.git
  scm: git
  version: 2.0.0
  name: neo4j
```

or using [Ansible Galaxy](https://galaxy.ansible.com/idealista/neo4j_role/) as origin if you prefer:

```yml
- src: idealista.neo4j_role
  version: 2.0.0
  name: neo4j
```

Install the role with ansible-galaxy command:

```sh
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

```yml
---
- hosts: someserver
  roles:
    - neo4j
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see the possible configuration properties.

Check in the maven section how can you set up a oracle maven repository.

You can edit neo4j config and dashboards via template or webui.

## Testing

```sh
pipenv install -r test-requirements.txt
pipenv run molecule test
```

## Built With

![Ansible](https://img.shields.io/badge/ansible-2.8.6-green.svg)

## Versioning

For the versions available, see the [tags on this repository](https://github.com/idealista/neo4j_role/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors

- **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/neo4j_role/contributors) who participated in this project.

## License

![Apache 2.0 License](https://img.shields.io/hexpm/l/plug.svg)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Additional Doc

- [Neo4j Operations Manual](https://neo4j.com/docs/operations-manual/current/introduction/)
