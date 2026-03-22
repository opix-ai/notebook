# poetry
[`poetry`](https://python-poetry.org/) is for Python package management and
dependency management.

## Installation
Please follow the instructions of the [official installer](
https://python-poetry.org/docs/#installing-with-the-official-installer)

## Configuration
The default directory to store the virtual environments is `~/.cache/pypoetry`.
Be aware that this is going to grow large depending on the number of them and
the packages they have. So, if you want to use another directory, possibly in
a mounted disk, run the following:
```bash
poetry config cache-dir /path/to/pypoetry
```

To get started you need Poetry's bin directory ($HOME/.local/bin) in your `PATH`
environment variable.

Add `export PATH="$HOME/.local/bin:$PATH"` to your shell configuration file
(~/.bashrc).

## Creating a new project
To create a new project with poetry as a dependency manager, follow the steps.
```bash
poetry new wow_project  # Create the project structure
cd wow_project
```

*IMPORTANT:* If the Python version you will use for the `wow_project` is 
not the global version you have set with [`pyenv`](pyenv.md), then run
the following command:
```bash
poetry env use ~/.pyenv/versions/3.12.1/bin/python
```
For more information refer to the official [project setup guide](
https://python-poetry.org/docs/master/basic-usage/#project-setup).

Initialize the git repository and create a virtual environment associated
with the project:
```bash
git init
poetry shell
```

## Initialising a pre-existing project
Instead of creating a new project, [`poetry`] can be used to ‘initialise’ a
pre-populated directory. To interactively create a `pyproject.toml` file in
directory pre-existing-project:
```bash
cd pre-existing-project
poetry init
```

## Activating the virtual environment
The easiest way to activate the virtual environment is to create a nested
shell with `poetry shell`.

To deactivate the virtual environment and exit this new shell type `exit`. To
deactivate the virtual environment without leaving the shell, type `deactivate`.

Read more [here](
https://python-poetry.org/docs/master/basic-usage/#activating-the-virtual-environment).

## Managing dependencies
Poetry provides a way to organize your dependencies by groups. For instance,
you might have dependencies that are only needed to test your project or to
build the documentation.

To add a package required by the project, run:
```bash
poetry add pandas
```

An optional, but highly recommended group, is the development one. To add a
package to the development group, run:
```bash
poetry add pytest --group dev
```

For details, please read the [documentation](
https://python-poetry.org/docs/managing-dependencies/)
