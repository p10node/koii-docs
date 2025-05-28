---
title: Install the Koii CLI Suite
description: How to install the Koii CLI Suite?
image: img/thumbnail.png
sidebar_label: Install the Koii CLI Suite
---

import Description from "@site/src/components/description";

<!-- <Description
  text="To interact with the K2 locally, you need to install the Koii CLI. The Koii CLI provides a set of valuable features, including:Generating a Koii wallet,Running Koii test validator."
/> -->

## Prerequisites

Before installing the Koii CLI, ensure you have:
- A stable internet connection
- Administrator/sudo privileges
- For Windows: Windows 10 or later
- For MacOS: macOS 10.15 or later
- For Linux: Ubuntu 20.04+, Debian 10+, or equivalent

## Overview

To interact with the K2 network locally, you must install the Koii CLI. The Koii CLI is equipped with a range of essential features, such as:

1. Generating a Koii wallet: With the Koii CLI, you can easily create a wallet specifically designed for Koii interactions.

2. Running Koii test validator: The Koii CLI allows you to execute a test validator, enabling you to test and validate your Koii-related functionalities locally.

By using the Koii CLI, you can seamlessly interact with the K2 network within your local development environment, empowering you to build and test your applications efficiently.

# MacOS & Linux Installation

1. Open your terminal and execute the following command:

```sh
sh -c "$(curl -sSfL https://raw.githubusercontent.com/koii-network/k2-release/master/k2-install-init.sh)"
```

This command will download and install the necessary Koii tools.

2. Depending on your operating system, you may receive the following prompt:

```sh
Please update your PATH environment variable to include the koii programs:
```

If you encounter this message, proceed to the next step. Otherwise, move on to step 4.

3. Update your PATH environment variable:

   For Bash users:
   ```sh
   echo 'export PATH="$HOME/.local/share/koii/install/active_release/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc
   ```

   For Zsh users:
   ```sh
   echo 'export PATH="$HOME/.local/share/koii/install/active_release/bin:$PATH"' >> ~/.zshrc
   source ~/.zshrc
   ```

4. To confirm that your `PATH` environment variable has been successfully updated, run:

```sh
echo $PATH
```

5. Verify the installation by running:

```sh
koii --version
```

You should see the version information similar to this:

```sh
koii-cli 1.16.2
```

# Windows Installation

1. Open a Command Prompt (cmd.exe) as an Administrator:
   - Press Windows key
   - Type "Command Prompt" (or cmd)
   - Right-click and select "Run as administrator"
   - Click "Yes" if prompted by User Account Control

2. Create a temporary directory and download the installer:
   ```sh
   mkdir C:\koii-install-tmp
   cd C:\koii-install-tmp
   curl -L https://github.com/koii-network/k2-release/releases/latest/download/koii-install-init-x86_64-pc-windows-msvc.exe --output koii-install-init.exe
   ```

   :::tip Alternative Download
   If the above command doesn't work:
   1. Visit the [latest release page](https://github.com/koii-network/k2-release/releases/latest)
   2. Download `koii-install-init-x86_64-pc-windows-msvc.exe`
   3. Move it to `C:\koii-install-tmp\koii-install-init.exe`
   :::

3. Run the installer:
   ```sh
   koii-install-init.exe
   ```
   - If Windows Defender or antivirus blocks the installation, click "More info" and then "Run anyway"

4. Close the current Command Prompt and open a new one as a normal user

5. Verify the installation:
   ```sh
   koii --version
   ```

# Configuration

After installation, you need to configure your RPC endpoint:

1. For Testnet (default):
   ```sh
   koii config set --url https://testnet.koii.network
   ```

2. For Mainnet:
   ```sh
   koii config set --url https://mainnet.koii.network
   ```

# Troubleshooting

## Common Issues

1. **Command not found after installation**
   - Ensure you've added the PATH to your shell configuration file
   - Restart your terminal
   - For Windows, ensure you're running as a normal user, not administrator

2. **Permission denied errors**
   - For MacOS/Linux: Run `chmod +x ~/.local/share/koii/install/active_release/bin/koii`
   - For Windows: Run Command Prompt as administrator

3. **Antivirus blocking installation**
   - Temporarily disable antivirus
   - Add an exception for the Koii installation directory

## Updating the CLI

To update to the latest version:

```sh
koii-install update
```

## Uninstallation

To remove the Koii CLI:

1. MacOS/Linux:
   ```sh
   rm -rf ~/.local/share/koii
   ```

2. Windows:
   ```sh
   rmdir /s /q %USERPROFILE%\.local\share\koii
   ```

Need help? Join our [Discord community](https://discord.com/invite/koii-network) for support.
