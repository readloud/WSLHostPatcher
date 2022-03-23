1. INSTALL [WSL 2](https://aka.ms/PSWindows)

  - Upgrade WSL to latest vesion
~~~
iex "& { $(irm https://aka.ms/install-powershell.ps1) } -UseMSI"
~~~

  - RUN POWERSHELL as administrator
~~~
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
~~~

  - RESTART
~~~
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
~~~

  - CHECK VERSION
~~~
systeminfo | find "System Type"
wsl --list --verbose
~~~

  - SET DEFAULT TO WSL 2
~~~
wsl --set-default-version 2
~~~

2. INSTALL GUI
~~~
wsl --install -d kali-linux
~~~

  - SET PASSWORD & USERNAME (OPTIONAL)
~~~
wsl -d kali-linux -u username
passwd root
~~~
~~~
wsl --shutdown
wsl --setdefault Kali-linux
wsl -d kali-linux -u username
kali config --default-user username
~~~
~~~
sudo apt update && sudo apt upgrade -y
sudo apt install kali-desktop-xfce -y
sudo apt install -y kali-linux-large
sudo apt-get install kali-linux-default
~~~
  - or
~~~
wget https://gitlab.com/kalilinux/build-scripts/kali-wsl-chroot/-/raw/master/xfce4.sh
chmod+x xfce4.sh
sudo./x fce4.sh
~~~

3. XRDP
~~~
sudo apt install xrdp -y
sudo service xrdp start
~~~

  - Optional Installation
~~~
docker pull kalilinux/kali-rolling
docker run --tty --interactive kalilinux/kali-rolling /bin/bash
sudo apt update && sudo apt -y install kali-linux-headless
~~~
~~~
git clone https://github.com/RoliSoft/WSL-Distribution-Switcher.git
cd WSL-Distribution-Switcher
python get-prebuilt.pykalilinux/kali-linux-docker
python install.pyrootfs_kalilinux_kali-linux-docker_latest.tar.gz
lxrun/set default user root
https://github.com/belherdigital/documentation-oe.git
~~~

  - Optional Configuration
~~~
- /etc/ssl/openssl.cnf
- /etc/ssl/kali.cnf
- /etc/samba/smb.conf
- /etc/ssh/ssh_config.d/kali-wide-compat.conf
- regenerate-ssh-host-keys
- /etc/ssh
~~~
~~~
sudo systemctl disable regenerate-ssh-host-keys.service
~~~

  - Optional Addition
~~~
/etc/apt/sources.list
grep -v '#' /etc/apt/sources.list | sort -u
echo "deb http://http.kali.org/kali kali-rolling main contrib non-free" | sudo tee /etc/apt/sources.list
echo "deb http://http.kali.org/kali kali-last-snapshot main contrib non-free" | sudo tee /etc/apt/sources.list
echo "deb http://http.kali.org/kali kali-experimental main contrib non-free" | sudo tee /etc/apt/sources.list.d/kali-experimental.list
echo "deb http://http.kali.org/kali kali-bleeding-edge main contrib non-free" | sudo tee /etc/apt/sources.list.d/kali-bleeding-edge.list
~~~

  - Remove Optional addition
~~~
sudo rm /etc/apt/sources.list.d/kali-experimental.list
sudo rm /etc/apt/sources.list.d/kali-bleeding-edge.list
echo "deb-src http://http.kali.org/kali kali-rolling main contrib non-free" | sudo tee -a /etc/apt/sources.list
cat /etc/apt/sources.list
sudo tee /etc/apt/sources.list.d/kali-bleeding-edge.list
sudo rm -f /etc/apt/sources.list.d/kali-bleeding-edge.list
sudo apt install gitleaks/kali-bleeding-edge
sudo apt install gitleaks/kali-rolling
~~~
