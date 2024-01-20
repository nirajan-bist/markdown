# Windows Terminal
- Install Windows Terminal form store.
- While holding `Ctrl + Shift` click Settings options form the dropdown of terminal To open user setting.
- Add schemes from [Gist](https://gist.github.com/nirajan-bist/021ca82d98a9361105959e08a638cfaa).
- Use Any Nerd Font in the Default > Appearance eg.(`Roboto Mono Nerd Font, MesloLG, FiraCode`) [Link](https://www.nerdfonts.com/font-downloads)
- Enable Acrylic Bakground shadow (Dark+ theme).


# Docker in WSL 2
- Install Ubuntu without version from store.
- Run
```Powershell
wsl.exe -l -v # List the version of installed distros
wsl.exe --update
wsl.exe --set-version Ubuntu 2 # Sets WSL 2 for Ubuntu
wsl.exe --set-default-version 2
wsl --set-default Ubuntu
```
- Run [Reference Link](https://nickjanetakis.com/blog/install-docker-in-wsl-2-without-docker-desktop)
```bash
# Install Docker, you can ignore the warning from Docker about using WSL
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

# Add your user to the Docker group
sudo usermod -aG docker $USER

# Sanity check that both tools were installed successfully
docker --version
docker compose version

# Using Ubuntu 22.04 or Debian 10+? You need to do 1 extra step for iptables
# compatibility, you'll want to choose option (1) to use iptables-legacy from
sudo update-alternatives --config iptables
```

# Git Setup
- Run follwing for setting global email and name
```bash
git config --global user.email "bistneon@gmail.com"
git config --global user.name "Nirajan Bist"
git config --global core.editor "vim"
```
- Run following script for setting ssh keys.
```bash
ssh-keygen -t ed25519 -C "bistneon@gmail.com"
eval `ssh-agent`
ssh-add

```
- Add Output of `cat ~/.ssh/id_ed25519.pub` as SSH key in [github ssh keys](https://github.com/settings/ssh)


# VSCode Setup
- Install Extensions
  - Prettier
  - GitLens
  - WSL
  - Markdown
  - Bharyang
  - Code Spell Checker
- Remove `Ctrl + Q` keybindings from User settings conflicting with --VIM-BLOCK--
- Add `Ctrl + K, Ctrl + Up Arrow` for Uppercase
- Add `Ctrl + K, Ctrl + Down Arrow` for Lowercase
- Change Terminal Font to Nerd Font eg. `Roboto Mono Nerd Font Mono`

# ZSH Setup
- Install __zsh__: `sudo apt install zsh`
- Install __oh-my-zsh__: `sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
- Clone theme __powerlevel10k__: `git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k`
- Clone zsh plugin _zsh-autosuggestions_: `git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`
- Clone zsh plugin _zsh-syntax-highlighting_: `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`
- Update `~/.zshrc` with following config.
```bash
  ZSH_THEME="powerlevel10k/powerlevel10k"

  plugins=(
    git
    zsh-autosuggestions
    zsh-syntax-highlighting
  )
```

# Node Setup via NVM
```bash
sudo apt-get update
sudo apt install curl 
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash 
nvm install node #installs latest version of node
```

# Git Scripts

# Datagrip

# Powertoys
- Keymap `Capslock` to `Esc`

