# Cellphone for work

Making a cellphone can work like a pc for coding, studying or working everywhere.

## Softwares

1. [Ternux](https://termux.dev/en/), [Ternux github repo](https://github.com/termux/termux-app) for android, [ish](https://ish.app/) for ios.
2. [Code Editor - Compiler & IDE](https://play.google.com/store/apps/details?id=com.rhmsoft.code&hl=en_US&gl=US) for android, [IOS version](https://apps.apple.com/us/app/code-editor-compiler-ide/id1581290510)
3. [Juicessh](https://juicessh.com/)
4. [Remote Desktop](https://play.google.com/store/apps/details?id=com.microsoft.rdc.androidx&hl=en_US&gl=US) for android.

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
ssh user@1.2.3.4 -p
```

### Commands for initialized
```
pkg install root-repo x11-repo -y
pkg upgrade -y
pkg update -y
pkg install -y vim-gtk git openssh
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

## NOTES
1. The project has canceled.
