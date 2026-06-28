# Install Termux on Android

# Do NOT use Play Store to Install Termux

The following instructions install the offical `termux` package downloaded from github repository.

# FIRST, Give Permission to Chrome App

We will describe how to install the Termux apk file via Chrome app, but first you need to enable your Chrome app to install unknown app.

1. Go to `Settings` > `Apps` > `Special app access` > `Install unknown apps`

2. Select Chrome

3. Enable "Allow from this source"

<b>Remarks:</b> You may disable this feature after you install Termux app.

# Install Termux App

1. Launch Chrome on your Android device.

2. Go to official Termux GitHub release page: https://github.com/termux/termux-app/releases

3. Download the "universal" version from the list under "Assets"

4. After the file is downloaded, select it from Chrome download list

5. Select "Install"

Extra step for Android 14+ users, read https://github.com/agnostic-apollo/Android-Docs/blob/master/en/docs/apps/processes/phantom-cached-and-empty-processes.md#commands-for-android-14-and-higher

# Install Repositories

Launch Termux and run,

> pkg install root-repo

> pkg install x11-repo

# Update and Upgrade

> pkg upgrade

# Termux:API & termux-api

Termux:API app and termux-api package are two different elements that needed to be installed separately.

1. Download and install a `*.apk` file from https://github.com/termux/termux-api/releases

2. Run in termux:

> pkg install termux-api

Read more at https://wiki.termux.com/wiki/Termux:API

# Storage Setup

Go to `Settings` > `Apps` > `Termux` > `Permissions` > `Files` > `Allow`

> termux-setup-storage

Locate the shared storage in `$HOME/storage`

Read more at https://wiki.termux.com/wiki/Sharing_Data

# Install Basic Packages

```
pkg install bash-completion which python golang git binutils libjpeg-turbo libpng build-essential clang make cmake pkg-config curl wget lynx w3m elinks vlc xclip xsel vim libxml2 libxslt python-apsw libzmq libsodium libgmp libmpc libmpfr python-lxml micro nano rust proot python-torch python-torchaudio python-torchvision
echo 'alias micro="micro -softwrap true -wordwrap true"' >> ~/.bashrc
source ~/.bashrc
```

Remarks:

1. We install the official python-apsw package created by Termux team, rather than using pip3, in order to work with regular expression searches.  For details, read https://github.com/termux/termux-packages/issues/12340

2. Installation of `rust` is necessary for several python packages to be installed.

Read more at: https://wiki.termux.com/wiki/Python#Python_module_installation_tips_and_tricks

# More about Packages

https://wiki.termux.com/wiki/Package_Management#Other_Package_Managers

https://wiki.termux.com/wiki/Python

# Install matplotlib on Termux

On Termux, do not use pip3 to install matplotlib, we manage to install matplotlib on Termux by running:

```
pip3 install 'kiwisolver<1.4.0,>=1.0.1' --force-reinstall
pip3 install cycler
pip3 install fonttools
pip3 install python-dateutil
pkg install python-numpy
pkg install matplotlib
```
