# Tmux Configuration

Personal tmux configuration with vim-style navigation and custom keybindings.

## Requirements

### Minimum Versions
- **tmux**: 2.1 or later (3.0+ recommended)
- **git**: Any recent version for plugin management

### System Compatibility
- macOS (tested on macOS Sonoma)
- Linux (most distributions)
- BSD systems

## Features

- 256-color and true color (RGB) support
- Mouse support enabled
- Custom prefix key (`Ctrl+a` instead of `Ctrl+b`)
- Vim-style window navigation
- Quick configuration reload
- Status bar at top
- Enhanced pane management
- Vim-tmux integration for seamless navigation
- Session logging capabilities

## Dependencies

This configuration uses [TPM (Tmux Plugin Manager)](https://github.com/tmux-plugins/tpm) to manage plugins. The following plugins are automatically installed:

1. **[tpm](https://github.com/tmux-plugins/tpm)** - Plugin manager itself
2. **[tmux-sensible](https://github.com/tmux-plugins/tmux-sensible)** - Sensible defaults for tmux
3. **[tmux-pain-control](https://github.com/tmux-plugins/tmux-pain-control)** - Better pane management keybindings
4. **[tmux-logging](https://github.com/tmux-plugins/tmux-logging)** - Easy session logging
5. **[vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator)** - Seamless navigation between vim and tmux panes
6. **[tmux-mountain-theme](https://github.com/Tecu23/tmux-mountain-theme)** - Custom mountain-inspired theme

## Installation

### 1. Install tmux

**macOS (Homebrew):**
```bash
brew install tmux
```

**Ubuntu/Debian:**
```bash
sudo apt install tmux
```

**Arch Linux:**
```bash
sudo pacman -S tmux
```

### 2. Install TPM (Tmux Plugin Manager)

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

### 3. Clone this configuration

If using as a standalone repo:
```bash
git clone git@github.com:tecu23/tmux.git ~/.config/tmux
```

If using as part of dotfiles (recommended):
```bash
# This is handled by the dotfiles install script
# See: https://github.com/tecu23/dotfiles-new
```

### 4. Install plugins

Start tmux:
```bash
tmux
```

Inside tmux, install plugins:
```
Ctrl+a I
```
(That's prefix + capital I)

## Configuration Details

### Custom Prefix
The default prefix (`Ctrl+b`) has been changed to `Ctrl+a` for easier access:
```
Prefix: Ctrl+a
```

### Key Bindings

#### General
- `Ctrl+a` - Prefix key
- `Ctrl+a r` - Reload configuration
- `Ctrl+a ?` - List all keybindings (default tmux binding)

#### Window Navigation
- `Alt+Shift+H` - Previous window (no prefix needed)
- `Alt+Shift+L` - Next window (no prefix needed)

#### Pane Navigation (vim-tmux-navigator)
- `Ctrl+h` - Move to left pane
- `Ctrl+j` - Move to lower pane
- `Ctrl+k` - Move to upper pane
- `Ctrl+l` - Move to right pane

#### Pane Management (tmux-pain-control)
- `Prefix + h/j/k/l` - Navigate panes
- `Prefix + H/J/K/L` - Resize panes
- `Prefix + |` - Split pane vertically
- `Prefix + -` - Split pane horizontally
- `Prefix + <` - Move window left
- `Prefix + >` - Move window right

#### Session Logging (tmux-logging)
- `Prefix + Shift+p` - Toggle logging
- `Prefix + Alt+p` - Screenshot current pane
- `Prefix + Alt+Shift+p` - Save complete pane history

### Settings

```bash
set -g default-terminal "xterm-256color"     # Enable 256 colors
set -ga terminal-overrides ',xterm-256color:RGB'  # True color support
set -sg escape-time 0                        # No delay for escape key
set -g mouse on                              # Enable mouse support
set-option -g history-limit 10000            # Increase scrollback buffer
set -g status-position top                   # Status bar at top
```

## Usage

### Starting tmux
```bash
tmux
```

### Creating sessions
```bash
tmux new -s session-name
```

### Attaching to sessions
```bash
tmux attach -t session-name
# or shorthand
tmux a -t session-name
```

### Listing sessions
```bash
tmux ls
```

### Detaching from session
Inside tmux:
```
Ctrl+a d
```

## Updating Plugins

Inside tmux:
```
Ctrl+a U
```
(Prefix + capital U)

## Troubleshooting

### Colors not working properly
Ensure your terminal supports 256 colors and true color. Add this to your shell config:
```bash
export TERM=xterm-256color
```

### Plugins not loading
1. Verify TPM is installed: `ls ~/.tmux/plugins/tpm`
2. Inside tmux, reload config: `Ctrl+a r`
3. Install plugins: `Ctrl+a I`

### Vim-tmux navigator not working
Ensure you have the corresponding vim/neovim plugin installed:
```vim
" For vim-plug
Plug 'christoomey/vim-tmux-navigator'
```

## Customization

To modify this configuration:

1. Edit `tmux.conf`
2. Reload configuration:
   - Inside tmux: `Ctrl+a r`
   - Or restart tmux: `tmux kill-server && tmux`

## Resources

- [Tmux Manual](https://man.openbsd.org/tmux)
- [TPM Documentation](https://github.com/tmux-plugins/tpm)
- [Tmux Cheat Sheet](https://tmuxcheatsheet.com/)

## License

Personal configuration - feel free to use and modify as needed.
