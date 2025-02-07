
# Blob File Management

A command-line utility to manage files in Azure Blob Storage with Git-style commands: `pull`, `push`, and `diff`.

## Features

- **Pull**: Download a file from Azure Blob Storage.
- **Push**: Upload a local file to Azure Blob Storage.
- **Diff**: Compare local and remote files with colorized output.

## Requirements

- **Azure CLI**: [Install Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli)
- **Git**: For colorized diffs if `colordiff` is unavailable.
- **Bash or Zsh**: Works in both environments.

## Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/brunopedrazza/blob-file-management.git
   cd blob-file-management
   ```

2. **Environment Variables**: Create a `.env` file in the project’s root with:
   ```bash
   AZURE_STORAGE_ACCOUNT_NAME="your_account_name"
   AZURE_STORAGE_CONTAINER_NAME="your_container_name"
   ```

3. **Alias and Path**: Add these to your `~/.bash_profile`, `~/.bashrc`, or `~/.zshrc`:
   ```bash
   export BLOB_ENV_PATH="$HOME/path/to/your/project/.env"
   alias blob='bash $HOME/path/to/your/project/blob'
   ```
   Reload your profile:
   ```bash
   source ~/.bash_profile  # or ~/.zshrc for zsh
   ```

4. **Optional - Install `colordiff` for Colorized Diff**:
   ```bash
   # macOS
   brew install colordiff

   # Ubuntu/Debian
   sudo apt-get install colordiff
   ```

## Usage

- **Pull**:
   ```bash
   blob pull <local_file_path>
   ```

- **Push**:
   ```bash
   blob push <local_file_path>
   ```

- **Diff**:
   ```bash
   blob diff <local_file_path>
   ```

## Troubleshooting

- **Authorization**: Ensure you’re logged in:
   ```bash
   az login
   ```

- **Blob Environment Path**: Verify `BLOB_ENV_PATH` points to the correct `.env` location.

## Uninstall

Remove the alias and environment variable from your profile and reload:
```bash
source ~/.bash_profile  # or ~/.zshrc for zsh
```
