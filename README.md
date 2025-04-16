# setup-for-auto-completion-and-text-highlighting-on-linux-terminal
ZSH Setup Guide with Auto-Suggestions, Syntax Highlighting, and Persistent History



## 📋 Prerequisites
- Ubuntu/Debian-based Linux distribution
- sudo privileges

## 🛠 Installation

### 1. Install Required Packages
```bash
sudo add-apt-repository universe
sudo apt update
sudo apt install zsh zsh-syntax-highlighting zsh-autosuggestions
```
### 2. Initialize ZSH
```bash
zsh
```
## ⚙ Configuration
### 3. Configure Plugins
```bash
# Backup existing config
cp ~/.zshrc ~/.zshrcbackup

# Add plugins to .zshrc
echo "source $(dpkg -L zsh-autosuggestions | grep 'zsh$')" | tee -a ~/.zshrc
echo "source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" | tee -a ~/.zshrc
```
### 4. Apply Changes
```bash
zsh
source ~/.zshrc
```
## 🔄 Make ZSH Default Shell
```bash
chsh -s $(which zsh)
```
## ⚠ Fix Command History Persistence
### 5. Configure History Settings
```bash
# Edit zshrc with your preferred editor (nano, vim, code, etc.)
nano ~/.zshrc
```
Add these lines:
```zsh
# History configuration
HISTFILE="$HOME/.zsh_history"
HISTSIZE=500000
SAVEHIST=500000

setopt appendhistory
setopt INC_APPEND_HISTORY
setopt SHARE_HISTORY
```
### 6. Apply History Settings
```bash
source ~/.zshrc
```
### 7. Reboot your machine
## ✅ Verification
Test your setup:

  - Start typing a command to see auto-suggestions

  - Enter valid/invalid commands to see syntax highlighting

  - Check history persistence after terminal restart:
```bash
history | tail
```
