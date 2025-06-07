
# 🛠️ Web3 Development Setup on macOS

This guide walks you through setting up a complete Web3 development environment on macOS.

---

## ✅ Prerequisites

- macOS (Intel or Apple Silicon)
- [Homebrew](https://brew.sh/) installed
- [VS Code](https://code.visualstudio.com/) installed

---

## 🧰 Install Xcode Command Line Tools

These provide compilers, linkers, and developer headers.

```bash
xcode-select --install
```

> 🧑‍💻 A popup will appear. Click **"Install"**, and wait for it to finish.

---

## 📦 System & Dev Tooling

```bash
# Update Homebrew and existing packages
brew update && brew upgrade

# Install commonly needed tools for Rust, Node, Python, Solidity
brew install git cmake openssl pkg-config tree htop
```

> 💡 `cmake`, `openssl`, and `pkg-config` are optional but commonly needed by Rust and Node packages with native bindings.

---

## 🛠️ Git Configuration

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@domain.com"
```

---

## 🔧 Install Programming Languages

### 🦀 Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

### 🐹 Go

```bash
brew install go
go version
```

### 🟢 Node.js (via NVM)

```bash
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

```

### 🐍 Python

macOS includes Python 3 by default. Check with:

```bash
python3 --version
pip3 --version
```

---

## 🧱 Solidity Compiler

```bash
pip3 install solc-select
solc-select install 0.8.24
solc-select use 0.8.24
solc --version
```

---

## 🔍 Verify All Installations

```bash
clang --version
rustc --version
cargo --version
go version
node -v
npm -v
python3 --version
solc --version
```

---

## 💻 Recommended VS Code Extensions

| Extension                      | Description                                           |
| ------------------------------ | ----------------------------------------------------- |
| **GitLens**                    | Git history, authorship, and blame info              |
| **Prettier**                   | Auto code formatting                                 |
| **ESLint**                     | JavaScript/TypeScript linting                        |
| **Rust Analyzer**              | Rust language server for IntelliSense                |
| **Crates**                     | See crate versions and docs inside `Cargo.toml`      |
| **CodeLLDB**                   | Debugger for Rust and C++                            |
| **Go**                         | Full support for Go development                      |
| **Python**                     | IntelliSense, linting, testing for Python            |
| **Pylance**                    | High-performance Python language support             |
| **Solidity** (Juan Blanco)     | Syntax, linting, compiler for Solidity               |
| **Hardhat for VS Code**        | Optional support for Hardhat projects                |
| **npm Intellisense**           | Autocompletion for npm packages                      |
| **Path Intellisense**          | Autocomplete relative file paths                     |
| **Better Comments**            | Organize comments into alerts, queries, TODOs        |
| **TODO Highlight**             | Highlights TODOs and FIXMEs in code                  |
| **Code Spell Checker**         | Spell checker for code comments and strings          |

---

## (Optional) Hardhat installtion
- Hardhat is the solidity tooling environement in JS/TS.
- learn more about hardhat here: https://hardhat.org
```shell
# 1. Create a new folder for your project
mkdir my-hardhat-project && cd my-hardhat-project

# 2. Initialize a new Node.js project (generates package.json)
npm init -y

# 3. Install Hardhat locally
npm install --save-dev hardhat

# 4. Create a basic Hardhat project
npx hardhat

# When prompted:
# Choose "Create a basic sample project"
# Press Enter for the default options
# Approve installing dependencies when asked

# verify installtion
# Should print the Hardhat CLI help output
npx hardhat
# Run the default test file provided in the sample project
npx hardhat test
```

---

## (Optional) Install foundry
- Foundry, a fast, portable, and modular toolkit for Ethereum application development. 
- With Foundry, end to end smart contract developement happens in Solidity.

```shell
# 1. Download and run the installation script
curl -L https://foundry.paradigm.xyz | bash

# 2. Source the environment to get access to foundryup
. ~/.bashrc

# 3. Install Foundry tools (forge, cast, anvil)
foundryup

# verify installation
forge --version    # Should show version info
cast --version
anvil --version

# initialize a new project
# Create a new Forge project
forge init my-foundry-project

# Move into the project directory
cd my-foundry-project

# Run the default tests
forge test
```

---
