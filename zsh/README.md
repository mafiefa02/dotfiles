# Zsh Shell Configuration

Configuration for Zsh (Z Shell) with Powerlevel10k theme, syntax highlighting, and development tools integration.

## Features

- **Theme**: Powerlevel10k for fast, customizable prompt
- **Syntax Highlighting**: Real-time command syntax highlighting
- **Node.js**: NVM (Node Version Manager) integration
- **GPG**: Proper GPG agent configuration for signing
- **Instant Prompt**: Fast shell startup with P10k instant prompt

## Configuration Overview

### Powerlevel10k Theme
- Instant prompt for faster shell startup
- Customizable prompt with git status, directory info, and more
- Configuration file: `~/.p10k.zsh` (generated via `p10k configure`)

### Development Tools
- **NVM**: Automatic loading of Node Version Manager
- **GPG**: Proper TTY configuration for Git commit signing
- **Environment**: Custom environment loading from `~/.local/bin/env`

### Shell Enhancements
- **Syntax Highlighting**: Commands are highlighted as you type
- **Completion**: Enhanced tab completion via NVM bash completion

## Installation

### Prerequisites

1. **Install Zsh** (if not already installed):
   ```bash
   # macOS (usually pre-installed)
   brew install zsh

   # Set as default shell
   chsh -s $(which zsh)
   ```

2. **Install Powerlevel10k**:
   ```bash
   brew install powerlevel10k
   ```

3. **Install Zsh Syntax Highlighting**:
   ```bash
   brew install zsh-syntax-highlighting
   ```

4. **Install NVM**:
   ```bash
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
   ```

5. **Install a Nerd Font** (for Powerlevel10k icons):
   ```bash
   brew install font-jetbrains-mono-nerd-font
   ```

### Configuration Setup

1. **Copy the configuration**:
   ```bash
   cp .zshrc ~/.zshrc
   ```

   Or create a symlink:
   ```bash
   ln -sf "$(pwd)/.zshrc" ~/.zshrc
   ```

2. **Configure Powerlevel10k**:
   ```bash
   # Restart your terminal, then run:
   p10k configure
   ```

3. **Create environment file** (optional):
   ```bash
   mkdir -p ~/.local/bin
   touch ~/.local/bin/env
   ```

## Configuration Details

### Instant Prompt
The configuration enables Powerlevel10k's instant prompt feature for faster shell startup. The prompt appears immediately while the full configuration loads in the background.

### Path Configuration
- Powerlevel10k theme: `/opt/homebrew/share/powerlevel10k/powerlevel10k.zsh-theme`
- Syntax highlighting: `/opt/homebrew/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh`
- NVM directory: `$HOME/.nvm`

### Environment Variables
- `GPG_TTY`: Set to current TTY for GPG operations
- `NVM_DIR`: Node Version Manager directory

### Automatic Loading
- NVM shell integration with bash completion
- GPG agent launch on shell startup
- Custom environment variables from `~/.local/bin/env`

## Customization

### Adding Aliases
Add your aliases to `~/.local/bin/env`:
```bash
echo "alias ll='ls -la'" >> ~/.local/bin/env
echo "alias gs='git status'" >> ~/.local/bin/env
```

### Modifying the Prompt
Run the configuration wizard:
```bash
p10k configure
```

### Additional Plugins
You can add more Zsh plugins by sourcing them in `.zshrc`:
```bash
# Example: Add autosuggestions
brew install zsh-autosuggestions
echo "source /opt/homebrew/share/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc
```

## Troubleshooting

### Slow Shell Startup
- Check if instant prompt is enabled
- Profile startup time: `time zsh -i -c exit`
- Consider removing heavy plugins

### Powerlevel10k Not Working
- Ensure you're using a Nerd Font in your terminal
- Verify the theme path exists: `/opt/homebrew/share/powerlevel10k/`
- Reconfigure: `p10k configure`

### NVM Issues
- Check if NVM directory exists: `ls ~/.nvm`
- Verify installation: `command -v nvm`
- Reinstall if necessary

### GPG Problems
- Test GPG: `echo "test" | gpg --clearsign`
- Check agent: `gpg-agent --version`
- Restart agent: `gpgconf --kill gpg-agent`

## Performance Tips

1. Use instant prompt (already enabled)
2. Minimize plugins and heavy operations in `.zshrc`
3. Use `~/.local/bin/env` for environment-specific settings
4. Consider lazy-loading heavy tools

## File Structure

```
~/.zshrc                    # Main Zsh configuration
~/.p10k.zsh                 # Powerlevel10k configuration (auto-generated)
~/.local/bin/env            # Custom environment variables and aliases
~/.nvm/                     # Node Version Manager
```

## Notes

- The configuration assumes Homebrew is installed in `/opt/homebrew/` (Apple Silicon)
- For Intel Macs, paths may be `/usr/local/share/`
- GPG configuration is essential for Git commit signing
- The instant prompt cache is stored in `$XDG_CACHE_HOME` or `$HOME/.cache`
