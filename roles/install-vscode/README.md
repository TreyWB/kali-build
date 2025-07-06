# Install VS Code Role

This role installs Visual Studio Code and configures it with a set of extensions. It includes intelligent checking to skip installation if all required extensions are already installed.

## Features

- Installs Visual Studio Code using the `gantsign.visual-studio-code` role
- Configures VS Code with a predefined set of extensions
- Checks if extensions are already installed to avoid unnecessary reinstallation
- Provides debug output to show installation status

## Default Extensions

The role installs the following extensions by default:

- `akamud.vscode-theme-onedark` - One Dark theme
- `KevinRose.vsc-python-indent` - Python indentation
- `vscodevim.vim` - Vim keybindings
- `tomoki1207.pdf` - PDF viewer
- `mechatroner.rainbow-csv` - CSV syntax highlighting
- `tamasfe.even-better-toml` - TOML support
- `ms-python.python` - Python extension

## Variables

### `vscode_extensions` (list)
List of VS Code extension IDs to install. Defaults to the extensions listed above.

### `users` (list)
List of user configurations for VS Code. This variable is passed directly to the `gantsign.visual-studio-code` role. Defaults to the current user with the default extensions.

## Example Usage

### Basic usage (uses defaults):
```yaml
- hosts: localhost
  roles:
    - install-vscode
```

### Custom extensions:
```yaml
- hosts: localhost
  vars:
    vscode_extensions:
      - ms-python.python
      - vscodevim.vim
      - akamud.vscode-theme-onedark
  roles:
    - install-vscode
```

### Multiple users:
```yaml
- hosts: localhost
  vars:
    users:
      - username: "user1"
        visual_studio_code_extensions:
          - ms-python.python
      - username: "user2"
        visual_studio_code_extensions:
          - vscodevim.vim
  roles:
    - install-vscode
```

## Dependencies

This role depends on the `gantsign.visual-studio-code` role, which should be available in your Ansible Galaxy collection. 