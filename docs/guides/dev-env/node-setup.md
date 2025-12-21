---
title: Node.js Environment Setup
---

# Node.js Environment Setup

This guide explains how to install and manage Node.js using Node Version Manager (NVM).
By using NVM, you can easily install and manage multiple versions of Node.js.

## 1. Installing NVM

First, you need to install NVM. Run the following command to install NVM:

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
```

This command downloads and runs the NVM installation script. After installation, reload the shell environment to use the NVM command:

```
source ~/.bashrc
```

## 2. Verifying NVM Installation

To verify that NVM is installed correctly, run the following command:

```
command -v nvm
```

If the installation is successful, the path to the `nvm` command will be displayed.

## 3. Checking LTS Versions

NVM allows you to install various versions of Node.js. To check the available LTS (Long-Term Support) versions, run the following command:

```
nvm list-remote | grep "Latest LTS"
```

This command may output something like:

```
v4.9.1   (Latest LTS: Argon)
v6.17.1   (Latest LTS: Boron)
v8.17.0   (Latest LTS: Carbon)
v10.24.1   (Latest LTS: Dubnium)
v12.22.12   (Latest LTS: Erbium)
v14.21.3   (Latest LTS: Fermium)
v16.20.0   (Latest LTS: Gallium)
v18.16.0   (Latest LTS: Hydrogen)
```

Choose the LTS version you want to install from this list.

## 4. Installing Node.js Version

To install a specific version of Node.js, run the following command. For example, to install Node.js v16.20.2, use:

```
nvm install v16.20.2
```

This command downloads and installs Node.js v16.20.2.

## 5. Verifying Node.js Version

Once installation is complete, run the following command to verify the installed Node.js version:

```
node -v
```

If everything is installed correctly, the output should be:

```
v16.20.2
```

## 6. Managing Multiple Node.js Versions

With NVM, you can install multiple versions of Node.js and easily switch between them. To list installed versions, use:

```
nvm ls
```

To switch to a specific version, use:

```
nvm use v16.20.2
```

This will activate Node.js v16.20.2.

## 7. Setting Default Node.js Version

To set a default Node.js version, use the following command:

```
nvm alias default v16.20.2
```

This ensures that Node.js v16.20.2 will be used by default in new terminal sessions.

## Conclusion

Through this guide, you learned how to easily install and manage Node.js using NVM. You can install and switch between multiple versions, which makes setting up your development environment much more efficient.
