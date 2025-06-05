# ⚙️ Developer Setup for Web3 on Windows with WSL2

Welcome! This guide is for anyone new to Web3 development who wants to set up their development environment on a **Windows PC** using **WSL2 (Windows Subsystem for Linux 2)** and **Ubuntu**.

---

## 🧠 What is WSL & Why Use It?

**WSL (Windows Subsystem for Linux)** allows you to run a full Linux environment directly on Windows without the need for a virtual machine or dual-boot setup.

### 🔁 WSL vs WSL2

| Feature        | WSL1                      | WSL2                                  |
| -------------- | ------------------------- | ------------------------------------- |
| Architecture   | Compatibility layer       | Full Linux kernel with virtualization |
| Performance    | Slower for many workflows | Much faster for file operations       |
| Docker Support | ❌ No                      | ✅ Yes                                 |
| System Calls   | Partial support           | Full support                          |

> **Use WSL2** — it provides better performance and full Linux compatibility.

---

## 🐧 Why Linux/Ubuntu for Web3 Development?

Most Web3 tools and blockchain development environments (e.g., Hardhat, Solidity, Rust-based chains, etc.) are **native to Linux**. Ubuntu is one of the most popular and beginner-friendly Linux distributions, with massive community support.

### ⚡ Benefits over native Windows:

* ✅ Linux CLI is faster and more powerful
* ✅ Native support for tools like `solc`, `nvm`, `rustup`, `go`
* ✅ Package managers (`apt`, `pip`, `cargo`) simplify installation
* ✅ No weird path or permission issues that occur on Windows

---

## 🧠 Prerequisites

* ✅ Install **Visual Studio Code (VSCode)** before anything else on windows.
  Download: [https://code.visualstudio.com/](https://code.visualstudio.com/)

---

## 🏗️ Setting Up WSL2 and Ubuntu

1. **Install WSL2**
   Follow the instructions under the **"Install WSL command"** section:
   👉 [https://learn.microsoft.com/en-us/windows/wsl/install](https://learn.microsoft.com/en-us/windows/wsl/install)

2. **Set Ubuntu as your distribution**
   You'll be prompted to create a **username and password** when Ubuntu runs for the first time.
   *(Password will not be visible while typing. Don't forget it!)*

3. **Having trouble?**
   Ping in the group with your error message and someone will help out.

---

## 💻 Accessing Ubuntu Files from Windows

You can browse Linux files from **Windows File Explorer**:
🗂️ Open Explorer → scroll down to `Linux > Ubuntu`

---

## 🧱 Installing Developer Tools

Open Ubuntu Terminal and run:

```bash
# Update package lists and upgrade installed packages
sudo apt update && sudo apt upgrade -y

# Install essential build tools and libraries for compiling code
sudo apt install -y build-essential gdb cmake clang curl tree htop libssl-dev pkg-config

# Install Git for version control
sudo apt install -y git
```

### 🔧 Set up Git

```bash
# Set your Git username (used in commit metadata)
git config --global user.name "Your Name"

# Set your Git email (used in commit metadata)
git config --global user.email "youremail@domain.com"
```

---

## 🧑‍💻 Installing Programming Languages

```bash
# 🔸 RUST
# Download and run the official Rust installation script
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Load Rust environment into the current terminal session
source $HOME/.cargo/env

# 🔸 GO
# Download Go 1.22.3 tarball
wget https://go.dev/dl/go1.22.3.linux-amd64.tar.gz

# Extract and install Go to /usr/local
sudo tar -C /usr/local -xzf go1.22.3.linux-amd64.tar.gz

# Add Go to your PATH permanently
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc

# Reload shell configuration
source ~/.bashrc


# 🔸 NODEJS via NVM
# Install NVM (Node Version Manager)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash

# Load NVM into the current terminal session
. "$HOME/.nvm/nvm.sh"

# Install Node.js version 22 using NVM
nvm install 22

# Verify installed Node.js version
node -v

# Verify the currently active Node.js version in NVM
nvm current

# Check installed npm version
npm -v

# 🔸 Solidity Compiler
# Install solc-select via pip (tool to manage Solidity versions)
pip3 install solc-select

# Install Solidity compiler version 0.8.24
solc-select install 0.8.24

# Set Solidity compiler version 0.8.24 as default
solc-select use 0.8.24
```

---

## ✨ Hello World: Verify Your Setup

```bash
# Check C compiler version
gcc --version

# Check C++ compiler version
g++ --version

# Check Clang compiler version
clang --version

# Check Rust compiler and package manager versions
rustc --version
cargo --version

# Check Go version
go version

# Check Node.js and npm versions
node -v
npm -v

# Check Python version
python3 --version

# Check Solidity compiler version
solc --version
```

---

## 🥉 Recommended VS Code Extensions

| Extension                          | Purpose                                        |
| ---------------------------------- | ---------------------------------------------- |
| **Remote - WSL**                   | Connect VSCode to WSL2 Ubuntu                  |
| **GitLens**                        | Git history, blame, insights                   |
| **Code Spell Checker**             | Catch typos in code & comments                 |
| **TODO Highlight**                 | Highlight TODO, FIXME, etc.                    |
| **Better Comments**                | Color-code and organize comments               |
| **C/C++**                          | IntelliSense, debugging                        |
| **CMake Tools**                    | CMake integration for C/C++                    |
| **CodeLLDB**                       | Rust & C++ debugging support                   |
| **Rust Analyzer**                  | Rust IntelliSense, linting, autocomplete       |
| **Crates**                         | Manage `Cargo.toml` dependencies visually      |
| **Go**                             | IntelliSense, tests, formatting for Go         |
| **Solidity (by Juan Blanco)**      | Solidity syntax, compilation, and linting      |
| **Hardhat for VS Code** (optional) | Smart contract workflow (JS/TS)                |
| **ESLint**                         | JavaScript/TypeScript linting                  |
| **Prettier**                       | Auto-format code                               |
| **npm Intellisense**               | Autocomplete for `node_modules` imports        |
| **Path Intellisense**              | Autocomplete for file paths                    |
| **Python (by Microsoft)**          | IntelliSense, debugging, virtualenvs           |
| **Pylance**                        | Fast and feature-rich Python support           |

---

## 💡 Launching VS Code from Ubuntu Terminal

Once inside your Ubuntu terminal, run:

```bash
code .
```

> The first time you run this, it will set up the WSL integration and open VSCode in your Linux workspace.

---

## 🏁 You're Ready!

You now have a powerful Web3-ready dev environment with access to:

* Linux tools
* Multiple programming languages
* Blockchain and smart contract tooling
* Visual Studio Code integrated with WSL2

Happy building! 🚀

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