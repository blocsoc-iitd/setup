# Setup

- contains scripts necessary to equip a pc with necessary tooling for web3 development.
- Before setting up WSL2, make sure that VSCode is installed on your computer.

## Setting up WSL2 on windows and installing windows.

- follow this tutorial on installing wsl2, go to "Install WSL command" and follow the instructions there, if you never installed wsl on your system.
https://learn.microsoft.com/en-us/windows/wsl/install
- if you are stuck ping in the group, with the error. 
- Up on opening wsl2 or ubuntu for the first time, you will be prompted to enter username and password(password will not be visible while typing). Don't forget your password.

## Installing Dev Tools
- In the windows file explorer on the bottom left, you will find linux > ubuntu. Using this one can access files located in ubuntu.

- open ubuntu terminal and run:

```shell
sudo apt update && sudo apt upgrade -y # update all the packages
sudo apt install -y build-essential gdb cmake clang curl tree htop libssl-dev pkg-config # install build tools
sudo apt install git # install git
```

- setting up git

```shell
git config --global user.name "Your Name" # replace Your Name with your github username.
git config --global user.email "youremail@domain.com" # replace youremail with email used in github.
```

## Installing Languages
- we will install go, rust, nodejs, python(comes with ubuntu)

```shell
# installing rust
# enter this command in the terminal and follow the instructions. (choose default for everything)
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# to restart the shell
source $HOME/.cargo/env

# installing go
# download go1.22.3 tarball
wget https://go.dev/dl/go1.22.3.linux-amd64.tar.gz
# install
sudo tar -C /usr/local -xzf go1.22.3.linux-amd64.tar.gz
# setup env variables
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc
source ~/.bashrc

# installing nodejs
# Download and install nvm:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash

# in lieu of restarting the shell
\. "$HOME/.nvm/nvm.sh"

# Download and install Node.js:
nvm install 22

# Verify the Node.js version:
node -v # Should print "v22.16.0".
nvm current # Should print "v22.16.0".

# Verify npm version:
npm -v # Should print "10.9.2".

# install solidity compiler
pip3 install solc-select
solc-select install 0.8.24
solc-select use 0.8.24
```

## Hello World(s)
lets verify installations:
```shell
gcc --version
g++ --version
clang --version
rustc --version
cargo --version
go version
node -v
python3 --version
solc --version
```

## VS Code Extensions
| Extension              | Description                                     |
| ---------------------- | ----------------------------------------------- |
| **Remote - WSL**       | 👨‍💻 Use VS Code with WSL2 seamlessly          |
| **GitLens**            | 🔍 Git supercharged: blame, history, authorship |
| **Code Spell Checker** | 🔤 Catches typos in code and comments           |
| **TODO Highlight**     | ✅ Highlights TODO, FIXME, etc.                  |
| **Better Comments**    | 💬 Categorize and color-code comments           |
| **C/C++** (by Microsoft) | 🧠 IntelliSense, debugging, and linting   |
| **CMake Tools**          | ⚙️ Integrates with CMake                  |
| **CodeLLDB**             | 🐞 Debugger that works great for Rust/C++ |
| **Rust Analyzer** | ⚡ Best-in-class Rust support                     |
| **Crates**        | 📦 View versions and docs of `Cargo.toml` crates |
| **CodeLLDB**      | 🐞 Rust debugging support                        |
| **Go** (by Go Team) | 🔧 Official Go support (IntelliSense, test, fmt) |
| **Solidity** (by Juan Blanco)      | 💼 Syntax highlighting, linting, and compile |
| **Hardhat for Visual Studio Code** | 🚀 Hardhat support (optional)                |
| **ESLint**                         | 🧹 Linting for JavaScript/TypeScript         |
| **Prettier**                       | 💅 Auto code formatter                       |
| **npm Intellisense**               | 🧠 Autocomplete for npm modules              |
| **Path Intellisense**              | 📁 Autocomplete for file paths               |
| **Python** (by Microsoft) | 🧪 IntelliSense, debugging, linting, virtualenvs |
| **Pylance**               | ⚡ Fast Python language support                   |
| **Jupyter**               | 📓 For notebooks if needed                       |
