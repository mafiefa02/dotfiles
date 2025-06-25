# Ghostty Terminal Configuration

Configuration for the Ghostty terminal emulator - a fast, feature-rich terminal built with GPU acceleration.

## Features

- **Font**: JetBrains Mono at 14pt for excellent code readability
- **Theme**: GitHub Dark Dimmed for comfortable dark mode experience
- **Background**: Semi-transparent (88% opacity) with blur effect
- **Window**: Clean, minimalist appearance with hidden titlebar
- **Icon**: Custom X-ray icon for macOS

## Configuration Details

### Appearance
- Background opacity: 88% with 20px blur radius
- Window padding: 24px horizontal, 16px vertical (balanced)
- Hidden titlebar and proxy icon for clean look
- Empty title for minimal distraction

### Typography
- Primary font: JetBrains Mono (14pt)
- Window title font: JetBrains Mono (consistent styling)

### Color Scheme
Based on GitHub Dark Dimmed theme with custom palette:
- Background: `#22272e`
- Foreground: `#adbac7`
- Cursor: `#539bf5` (blue)
- Selection: Light text on dark background

## Installation

1. **Install Ghostty**: Download from [ghostty.org](https://ghostty.org)

2. **Install JetBrains Mono font**:
   ```bash
   brew install font-jetbrains-mono
   ```

3. **Copy configuration**:
   ```bash
   mkdir -p ~/.config/ghostty
   cp config ~/.config/ghostty/config
   ```

   Or create a symlink:
   ```bash
   ln -sf "$(pwd)/config" ~/.config/ghostty/config
   ```

## Customization

The configuration file supports many options:
- Adjust `font-size` for different display sizes
- Modify `background-opacity` for transparency preferences
- Change `window-padding-x/y` for different spacing
- Customize colors in the palette section

## Troubleshooting

- If font doesn't load, ensure JetBrains Mono is installed system-wide
- For blur effects, ensure you're running on macOS with supported hardware
- Transparency effects require compositor support on Linux
