# Dotfiles Configuration

This repository contains my personal configuration files for various applications and tools.

## Structure

```
dotfiles/
├── ghostty/          # Ghostty terminal emulator configuration
│   └── config        # Main configuration file
├── zed/              # Zed editor configuration
│   └── settings.json # Editor settings and preferences
├── zsh/              # Zsh shell configuration
│   └── .zshrc        # Shell configuration and aliases
└── README.md         # This file
```

## Applications

### Ghostty Terminal
- **File**: `ghostty/config`
- **Target**: `~/.config/ghostty/config`
- Modern terminal emulator with GPU acceleration
- Configured with JetBrains Mono font and GitHub Dark Dimmed theme

### Zed Editor
- **File**: `zed/settings.json`
- **Target**: `~/.config/zed/settings.json`
- Fast, collaborative code editor
- Configured with Vim mode, Fleet Dark theme, and Biome formatting

### Zsh Shell
- **File**: `zsh/.zshrc`
- **Target**: `~/.zshrc`
- Shell configuration with Powerlevel10k theme
- Includes NVM, GPG, and syntax highlighting setup

## Installation

### Manual Installation

```bash
# Ghostty
mkdir -p ~/.config/ghostty
cp ghostty/config ~/.config/ghostty/config

# Zed
mkdir -p ~/.config/zed
cp zed/settings.json ~/.config/zed/settings.json

# Zsh
cp zsh/.zshrc ~/.zshrc
```

### Symlink Installation (Recommended)

```bash
# Create symlinks to keep configurations in sync
mkdir -p ~/.config/ghostty ~/.config/zed

ln -sf "$(pwd)/ghostty/config" ~/.config/ghostty/config
ln -sf "$(pwd)/zed/settings.json" ~/.config/zed/settings.json
ln -sf "$(pwd)/zsh/.zshrc" ~/.zshrc
```

## Dependencies

Make sure you have these installed:

- **Powerlevel10k**: `brew install powerlevel10k`
- **Zsh Syntax Highlighting**: `brew install zsh-syntax-highlighting`
- **NVM**: [Node Version Manager](https://github.com/nvm-sh/nvm)
- **JetBrains Mono Font**: Available via Homebrew or direct download

## Notes

- The Zsh configuration assumes Homebrew is installed in `/opt/homebrew/`
- GPG configuration requires `gpg-agent` to be properly set up
- Some Zed language servers (like Biome) may need to be installed separately
