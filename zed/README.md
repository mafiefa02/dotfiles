# Zed Editor Configuration

Configuration for Zed - a high-performance, multiplayer code editor designed for speed and collaboration.

## Features

- **Theme**: Fleet Dark for a modern, comfortable coding experience
- **Font**: JetBrains Mono at 16pt with standard line height
- **Vim Mode**: Enabled for efficient text editing
- **AI Integration**: Claude Sonnet 4 for intelligent code assistance
- **Formatting**: Biome for JavaScript/TypeScript, Prettier as fallback
- **UI**: Minimal interface with hidden panels for distraction-free coding

## Configuration Highlights

### Editor Behavior
- Vim mode enabled for modal editing
- Relative line numbers for easier navigation
- Session restoration on startup
- Mouse hiding during typing and movement
- Format on save with automatic code actions

### Language Support
Specialized configurations for:
- **JavaScript/TypeScript**: Biome formatter with import organization
- **JSX/TSX**: React support with Biome formatting
- **Vue.js**: Component development with Biome integration

### Formatting & Code Actions
- **Global**: Prettier formatter with ESLint fixes
- **JS/TS**: Biome formatter with automatic imports and fixes
- **On Save**: Automatic formatting and import organization

### AI Agent
- **Provider**: Zed.dev (Claude Sonnet 4)
- **Features**: Code completion, explanations, and assistance
- **Version**: 2 (latest agent version)

### UI Customization
**Hidden Elements** (for clean interface):
- Tab bar
- Toolbar breadcrumbs and quick actions
- Most panel buttons (chat, collaboration, diagnostics, etc.)
- Scrollbars

**Visible Elements**:
- Git panel (docked right)
- Project panel (docked right, button hidden)

## Installation

1. **Install Zed**: Download from [zed.dev](https://zed.dev)

2. **Install required tools**:
   ```bash
   # Biome (JavaScript/TypeScript formatter)
   npm install -g @biomejs/biome

   # Prettier (fallback formatter)
   npm install -g prettier
   ```

3. **Copy configuration**:
   ```bash
   mkdir -p ~/.config/zed
   cp settings.json ~/.config/zed/settings.json
   ```

   Or create a symlink:
   ```bash
   ln -sf "$(pwd)/settings.json" ~/.config/zed/settings.json
   ```

## Language Server Setup

### Biome
- Requires `biome.json` config file in project root
- Provides fast formatting and linting for JS/TS
- Automatically organizes imports

### TypeScript
- Built-in language server support
- Enhanced with Biome for formatting
- Automatic type checking and IntelliSense

## Customization

### Themes
Available themes can be changed by modifying the `theme` setting:
- `"Fleet Dark"` (current)
- `"One Dark"`
- `"Solarized Dark"`
- `"Catppuccin"`

### Fonts
Modify font settings:
```json
{
  "buffer_font_family": "Your Font",
  "buffer_font_size": 14,
  "ui_font_size": 14
}
```

### Vim Mode
To disable Vim mode:
```json
{
  "vim_mode": false
}
```

## Privacy & Telemetry

Telemetry is disabled in this configuration:
- No diagnostic data collection
- No metrics reporting
- Privacy-focused setup

## File Exclusions

The configuration excludes common directories from file scanning:
- Version control (`.git`, `.svn`, etc.)
- Dependencies (`node_modules`, `.next`)
- System files (`.DS_Store`, `Thumbs.db`)
- IDE files (`.settings`, `.classpath`)

## Troubleshooting

- **Formatting issues**: Ensure Biome is installed and project has `biome.json`
- **Vim mode problems**: Check Zed's vim documentation for key bindings
- **Language server errors**: Verify TypeScript/JavaScript tools are installed
- **AI not working**: Check internet connection and Zed.dev service status
