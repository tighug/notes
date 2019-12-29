# Starship

- [Starship](https://starship.rs/)

## Installation

### 1. OS にインストールする

Mac

```bash
brew install starship
```

Linux

```bash
wget -q --show-progress https://github.com/starship/starship/releases/latest/download/starship-x86_64-unknown-linux-gnu.tar.gz
tar xvf starship-x86_64-unknown-linux-gnu.tar.gz
sudo mv target/x86_64-unknown-linux-gnu/starship /usr/local/bin/
```

### 2. `init`スクリプトを追加する

Bash

```bash
# ~/.bashrc

eval "$(starship init bash)"
```

Fish

```bash
# ~/.config/fish/config.fish

eval (starship init fish)
```

## Config - `starship.toml`

```yml
# ~/.config/starship.toml

add_newline = true
prompt_order = [
"username",
"hostname",
"kubernetes",
"directory",
"git_branch",
"git_state",
"git_status",
"package",
"dotnet",
"golang",
"java",
"nodejs",
"python",
"ruby",
"rust",
"nix_shell",
"memory_usage",
"aws",
"env_var",
"cmd_duration",
"line_break",
"jobs",
"battery",
"time",
"character",
]

[aws]
symbol = "☁️ "
style = "bold yellow"
disabled = true

[battery]
full_symbol = "•"
charging_symbol = "⇡"
discharging_symbol = "⇣"
disabled = true

[character]
symbol = "❯"
error_symbol = "❯"
use_symbol_for_status = true
vicmd_symbol = "❮"
style_success = "bold green"
style_failure = "bold red"
disabled = false

[cmd_duration]
min_time = 2
prefix = ""
style = "bold yellow"
disabled = false

[directory]
truncation_length = 0
truncate_to_repo = false
style = "bold cyan"
disabled = false

[env_var]

[git_status]


[line_break]
disabled = false

[memory_usage]
show_percentage = true
show_swap = false
threshold = 75
icon = " "
style = "bold dimmed red"
disabled = true

[nodejs]
symbol = "⬢ "
style = "green"
disabled = true

[package]
symbol = "📦 "
style = "red"
disabled = true
```
