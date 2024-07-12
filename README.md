# SSH Credentials Collector - Agent Plugin for Infection Monkey

## Introduction

SSH Credentials Collector is an Agent Plugin for
[Infection Monkey](https://www.akamai.com/infectionmonkey) that
steals SSH keys from compromised Linux machines.
It locates the SSH keys in the `/home` directory, steals SSH keypairs, and
uploads them to the Monkey Island server.
The supported private key encryption formats are RSA, DSA, EC and ECDSA.

For more information, see the [SSH Credentials Collector Plugin
documentation](https://techdocs.akamai.com/infection-monkey/docs/credential-collectors#ssh).

## Development
### Setting up the development environment

To create the resulting SSH archive, follow these steps:

1. **Clone the Repository**

    ```sh
    $ git clone https://github.com/guardicode/ssh-credentials_collector.git
    $ cd ssh-credentials_collector
    ```

1. **Install development dependencies**

    This project uses [Poetry](https://python-poetry.org/) for managing
    dependencies and virtual environments, and
    [pre-commit](https://pre-commit.com/) for managing pre-commit hooks.

    ```sh
    $ pip install pre-commit poetry
    $ pre-commit install -t pre-commit
    $ poetry install
    ```

### Running the test suite

The test suite can be run with the following command:

```sh
poetry run pytest
```

### Building the plugin

To build the plugin, run the [Agent Plugin
Builder](https://github.com/guardicode/agent-plugin-builder/).

```sh
poetry run build_agent_plugin .
```

The build tool will create `SSH-credentials_collector.tar`, which can be [installed in
the Monkey Island](https://techdocs.akamai.com/infection-monkey/docs/plugins).
