# pyenv
[`pyenv`](https://github.com/pyenv/pyenv) is a simple Python version manager.
Except the official documentation, a nice guide is [here](
https://realpython.com/intro-to-pyenv/)

## Build Dependencies
We need some packages for `pyenv` to build the Python versions. Run the
following command:
```bash
sudo apt-get install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \
libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl
```
## Installation
Install `pyenv`:
```bash
curl -fsSL https://pyenv.run | bash
```

Open the `~/.bashrc` file and append the following:
```
# Load pyenv automatically 
export PYENV_ROOT="$HOME/.pyenv"
[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init - bash)"

# Load pyenv-virtualenv automatically 
eval "$(pyenv virtualenv-init -)"
```

 Restart your shell for the changes to take effect.
```bash
exec $SHELL
```

## Usage
### Install Python versions
To list all the available Python versions to install, run:
```bash
pyenv install --list  # tip: use grep to filter
```

Once you find the version you want, you can install it with a single command:
```bash
pyenv install -v 3.12.0
```

### Using Python versions
Check what versions of Python you have available:
```bash
pyenv versions
* system (set by /home/aris/.pyenv/version)
3.8.12
3.11.4
```

The * indicates that the system Python version is active currently.
To use another version as system default, run:
```bash
pyenv global 3.11.4
```
