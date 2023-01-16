# Cellphone for work

Making a cellphone can work like a pc for coding, studying or working everywhere.

## Softwares

1. [Ternux](https://termux.dev/en/), [Ternux github repo](https://github.com/termux/termux-app) for android, [ish](https://ish.app/) for macOS.
2. [Code Editor - Compiler & IDE](https://play.google.com/store/apps/details?id=com.rhmsoft.code&hl=en_US&gl=US) for android, [IOS version](https://apps.apple.com/us/app/code-editor-compiler-ide/id1581290510)
3. [Juicessh](https://juicessh.com/) for android, [Secure ShellFish](https://secureshellfish.app/) for macOS.
4. [Remote Desktop](https://play.google.com/store/apps/details?id=com.microsoft.rdc.androidx&hl=en_US&gl=US) for all platforms.

## For start

### [Termux skills may be used](https://github.com/xingangshi/config_tools/blob/master/006_termux/termux_skills.md)

### Termux for ssh connecting

```
pkg install open-ssh -y
# start sshd
sshd
# close sshd
pkill sshd
# show sshd status
ps aux | grep sshd
```

Copy remote-login-client's public key which named id_ras.pub file content into the file `~/.ssh/authorized_keys` of termux-device.

```
# remote-login-client login
ssh u0_a252@192.168.101.3 -p8022 -i ~/.ssh/id_ras
```

### Commands for initialized
```
pkg install root-repo x11-repo -y
pkg upgrade -y
pkg update -y
pkg install -y vim-gtk git openssh rust
termux-setup-storage

mkdir .ssh storage/shared/termux_dir
ln -s storage/shared/termux_dir work

touch .ssh/id_rsa
cp -rf your_id_rsa_authorized .ssh/id_rsa

eval `ssh-agent`
ssh-add ~/.ssh/id_rsa

cd work
git clone your_git_repo
```

### Self softwares to install

#### [Vim install](https://github.com/xingangshi/vim_installer)

#### [Emacs prelude install](https://github.com/xingangshi/emacs_evil)

#### [Zsh install](https://www.zsh.org/)
```
pkg install zsh autjump -y

echo $SHELL
chsh -s zsh
echo $SHELL

git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
git clone https://github.com/zsh-users/zsh-autosuggestions \
    ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git \ 
    ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

git clone https://github.com/joelthelion/autojump.git
cd autojump %% ./install.py
```

<img width="1159" alt="msg of installing autojump" src="https://user-images.githubusercontent.com/44218078/212656262-fba4a54b-3e6a-48ea-bbab-2e44206bd4dc.png">

```
# update my oh-my-zsh plugins
# vim ~/.zshrc modify
#plugins=(git
#         zsh-autosuggestions
#         autojump
#         zsh-syntax-highlighting
#)
#
#[[ -s /data/data/com.termux/files/home/.autojump/etc/profile.d/autojump.sh ]] \
#  && source /data/data/com.termux/files/home/.autojump/etc/profile.d/autojump.sh
#autoload -U compinit && compinit -u
```

## NOTES
1. The project has canceled.
