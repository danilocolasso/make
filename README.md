# Static Make Binary

This repository contains a statically compiled Make binary, which is particularly useful for environments where root access is not available (such as Cloudways and other managed hosting services).

## Installation Instructions

### Option 1: Using the Pre-compiled Binary

1. Copy the `make` binary to your preferred directory (e.g., your home directory `~/`)
2. Make the binary executable:
   ```bash
   chmod +x make
   ```
3. Create an alias for easy access:
   ```bash
   alias make="$HOME/make"
   ```

### Option 2: Compiling from Source

If you prefer to compile your own version:

1. Download the desired version from the [GNU Make official website](https://ftp.gnu.org/gnu/make/)
2. Extract the downloaded archive
3. Navigate to the extracted directory
4. Compile with static linking:
   ```bash
   ./configure LDFLAGS="-static"
   make
   ```

> **Note:** You need build-essential installed to compile Make. If you don't have it, install it using:
> ```bash
> sudo apt update
> sudo apt install build-essential
> ```

After compilation, you'll find a `make` binary in the directory. Follow the steps from Option 1 to install it on your machine or server.

## Transferring to Remote Server

To transfer the binary to a remote server using SCP:
```bash
scp make user@your-server:/path/to/destination/
```