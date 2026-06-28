# Install Ubuntu Container

To run an Ubuntu environment on Android via Termux without requiring a rooted device (using proot):

Reference: https://github.com/jorexdeveloper/termux-ubuntu

```
# install ubuntu
cd
pkg update && pkg upgrade && pkg install -y git wget proot curl
curl -fsSLO https://raw.githubusercontent.com/jorexdeveloper/termux-ubuntu/main/install-ubuntu.sh
bash install-ubuntu.sh -y
# tweak audio
echo 'pulseaudio --start --load="module-native-protocol-tcp auth-ip-acl=127.0.0.1 auth-anonymous=1" --exit-idle-time=-1' >> ~/.bashrc
source ~/.bashrc
```

## Start Ubuntu

```
ubuntu
```

## Install Libraries

```
# basic
cd
apt update && apt full-upgrade
apt install -y bash-completion
apt install -y python3
apt install -y python3-setuptools python3-pip python3-dev python3-venv portaudio19-dev ffmpeg wget curl git wget nano micro sqlite3 libsqlite3-dev net-tools
apt install libxcb-cursor0 pulseaudio-utils alsa-base alsa-utils mpg123 espeak

# add missing group names
groupadd -g 3003 groupname3003
groupadd -g 9997 groupname9997
groupadd -g 20298 groupname20385
groupadd -g 50298 groupname50385

# Document conversion
sudo apt install pandoc texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended texlive-xetex

# text editor
echo 'alias micro="micro -softwrap true -wordwrap true"' >> ~/.bashrc

# support container sound output
echo 'export PULSE_SERVER=127.0.0.1' >> ~/.bashrc

# install golang
add-apt-repository ppa:longsleep/golang-backports
apt update
apt install golang-go

# add a local path
echo "export PATH=$HOME/.local/bin:$PATH" >> ~/.bashrc

# reload variables
source ~/.bashrc
```

## Exit Ubuntu

```
exit
```

## Useful Bultin Commands

Built-in command-line arguments to easily manage your Ubuntu installation:

Run in termux (NOT inside ubuntu), for example:

```
ubuntu --backup <archive-name>

ubuntu --restore <archive-name>

ubuntu --rename <new-directory>

ubuntu --uninstall
```

## Troubleshooting - not enough memory for undating man-db ...

```
sudo dpkg --configure -a
sudo apt --fix-broken install
sudo apt remove man-db
```