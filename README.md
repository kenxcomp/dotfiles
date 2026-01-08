# Dotfiles

Managed with [chezmoi](https://www.chezmoi.io/).

## New Mac Setup

### 1. Install Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### 2. Install chezmoi and apply dotfiles

```bash
brew install chezmoi
chezmoi init --apply kennethx
```

This will:
- Clone this repo
- Apply all dotfiles (including `~/Brewfile`)
- Auto-install fisher and plugins (via `run_once` script)
- Auto-install yazi plugins (via `run_once` script)

### 3. Install all dependencies via Brewfile

```bash
brew bundle --global
```

This installs all CLI tools, casks, fonts, and VS Code extensions.

### 4. Set fish as default shell

```bash
echo /opt/homebrew/bin/fish | sudo tee -a /etc/shells
chsh -s /opt/homebrew/bin/fish
```

## Daily Usage

| Task | Command |
|------|---------|
| Preview changes | `chezmoi diff` |
| Apply changes | `chezmoi apply` |
| Pull + apply updates | `chezmoi update` |
| Add new file | `chezmoi add ~/.config/xxx` |
| Edit managed file | `chezmoi edit ~/.config/xxx` |
| Re-sync from target | `chezmoi re-add ~/.config/xxx` |

## Theme Switching

Unified theme management for fish, kitty, zellij, yazi, btop, and nvim using chezmoi templates.

### Available Themes

| Theme | Type |
|-------|------|
| `gruvbox-material-dark` | Dark (default) |
| `catppuccin-mocha` | Dark |
| `catppuccin-macchiato` | Dark |
| `catppuccin-frappe` | Dark |
| `catppuccin-latte` | Light |

### Usage

```bash
# List available themes
theme-switch --list

# Switch to a theme
theme-switch catppuccin-mocha

# Show current theme
theme-switch --current
```

After switching, some tools may need manual reload:
- **Kitty**: Restart terminal or run `kitty @ set-colors --all ~/.config/kitty/current-theme.conf`
- **Zellij**: Exit and restart session
- **Btop**: Restart btop
- **Nvim**: Run `:colorscheme catppuccin-mocha` or restart

## What's Included

- **fish** - Shell config + plugins (pure theme)
- **kitty** - Terminal emulator config
- **zellij** - Terminal multiplexer config
- **nvim** - Neovim config (LazyVim)
- **yazi** - File manager config
- **btop** - System monitor config
- **aerospace** - Window manager
- **wezterm** - Terminal emulator (alternative)
- **zed** - Editor config
- **starship** - Prompt theme
- **borders** - Window borders
