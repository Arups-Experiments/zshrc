# 🐚 ZSH Configuration

This is a custom `.zshrc` configuration optimized for development productivity using **Oh My Zsh**, enhanced plugins, and convenient aliases. It is designed to work well on Linux-based systems with support for Git, Node.js, and shell improvements.

---

## 🚀 Features

- **Oh My Zsh** with the `miloshadzic` theme.
- Lazy loading for faster startup (especially for `nvm`).
- Custom prompt with hostname and current directory.
- Enhanced command-line experience via:
  - `zsh-autosuggestions`
  - `zsh-syntax-highlighting`
- Optimized PATH for tools like Yarn and Neovim.
- Useful aliases for Git, system control, clipboard utilities, and more.
- History configuration with a large buffer size.
- Helper functions for system update and Git log visualization.

---

## 📦 Prerequisites

Before using this configuration, ensure you have:

- Zsh installed (`zsh --version`)
- [Oh My Zsh](https://ohmyz.sh/) installed
- `nvm`, `yarn`, `git`, and `tmux` installed
- `xclip` installed (for `pbcopy` / `pbpaste` clipboard aliases)
- `preload` installed (optional for performance tuning)
- Plugins:
  - [`zsh-syntax-highlighting`](https://github.com/zsh-users/zsh-syntax-highlighting)
  - [`zsh-autosuggestions`](https://github.com/zsh-users/zsh-autosuggestions)

---

## 🛠️ Plugin Configuration

```zsh
plugins=(
  npm
  yarn
  git
  zsh-syntax-highlighting
  zsh-autosuggestions
)
```

Plugin settings:
- `nvm`: lazy loading enabled to reduce shell startup time.
- `yarn`: avoids using global path detection to reduce conflicts.
- Autosuggestions styled with underline, bold, and color.

---

## 🎨 Prompt Style

```zsh
PROMPT='%F{240}%n%F{red}@%F{green}%m:%F{141}%d$ %F{reset}'
```

This provides a clean and colorful shell prompt showing:
- Username
- Hostname
- Current directory

---

## 🧩 Useful Aliases

| Alias         | Description                             |
|---------------|-----------------------------------------|
| `tmux`        | Start tmux with UTF-8 support           |
| `pbcopy`      | Copy from stdin to clipboard (xclip)    |
| `pbpaste`     | Paste from clipboard                    |
| `python`      | Maps to `python3`                       |
| `reboot`      | Reboot system using systemd             |
| `shutdown`    | Shutdown system immediately             |
| `*.txt`       | Open `.txt` files with `vim`            |

---

## ⚙️ Helper Functions

### `timezsh`

Benchmark zsh startup time by running it 10 times:
```sh
timezsh
```

### `runpreload`

Start preload daemon (if installed):
```sh
runpreload
```

### `sysupgrade`

Update and upgrade all system packages:
```sh
sysupgrade
```

### `gitlog`

Display a clean and colorful Git commit graph:
```sh
gitlog
```

---

## 📝 History Settings

```zsh
HISTFILE=~/.zsh_history
HISTSIZE=10000
SAVEHIST=10000
```

This ensures up to 10,000 past commands are preserved across sessions.

---

## 🧠 Tips for Customization

- To add more plugins, place them in the `plugins=(...)` array.
- For a random theme every startup, set `ZSH_THEME="random"` and optionally define `ZSH_THEME_RANDOM_CANDIDATES`.
- Define personal aliases in the `ZSH_CUSTOM` directory or inside `.zshrc` directly.
- Customize prompt or theme using [Oh My Zsh Themes Wiki](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes).

---

## 📂 Path Adjustments

```zsh
export PATH="$PATH:$(yarn global bin)"
PATH+="$PATH:/opt/nvim-linux64/bin"
```

Adds Yarn global binaries and Neovim to your executable search path.

---

## 🔌 NVM Initialization

```zsh
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
```

Ensures Node Version Manager (NVM) is available in your shell.

---

## ✅ Final Load

At the end, the config sources `oh-my-zsh`:
```zsh
source $ZSH/oh-my-zsh.sh
```

---

## 📤 Contribution

Feel free to fork or copy this `.zshrc` to build your own custom configuration.
