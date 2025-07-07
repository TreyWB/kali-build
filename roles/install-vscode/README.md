# Install VS Code Role

This role installs Visual Studio Code and configures it with a set of extensions.

## Features

- Installs Visual Studio Code using the `gantsign.visual-studio-code` role
- Configures VS Code with a predefined set of extensions

## Default Extensions

List of extensions can be found in defaults/main.yml

## Variables

### `users` (list)
List of user configurations for VS Code. This variable is passed directly to the `gantsign.visual-studio-code` role. Defaults to the current user with the default extensions.

## Dependencies

This role depends on the `gantsign.visual-studio-code` role, which we store in requirements.yml