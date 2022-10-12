echo "deb http://http.kali.org/kali kali-rolling main non-free contrib" | sudo tee /etc/apt/sources.list
sudo apt update && sudo apt -y full-upgrade
cp -i /etc/skel/.bashrc ~/
cp -i /etc/skel/.zshrc ~/
chsh -s /bin/zsh
[ -f /var/run/reboot-required ] && sudo reboot -f

grep VERSION /etc/os-release

wget http://http.kali.org/kali/pool/main/k/kali-archive-keyring/kali-archive-keyring_2022.1_all.deb
sudo dpkg -i kali-archive-keyring_2022.1_all.deb
rm kali-archive-keyring_2022.1_all.deb
sudo apt-get update

`sudo apt -f update`
`sudo apt install -y kali-linux-headless`

System
kali-linux-core: Base Kali Linux System – core items that are always included
kali-linux-headless: Default install that doesn’t require GUI
kali-linux-default: “Default” desktop (amd64/i386) images include these tools
kali-linux-arm: All tools suitable for ARM devices
kali-linux-nethunter: Tools used as part of Kali NetHunter

Tools
kali-tools-gpu: Tools which benefit from having access to GPU hardware
kali-tools-hardware: Hardware hacking tools
kali-tools-crypto-stego: Tools based around Cryptography & Steganography
kali-tools-fuzzing: For fuzzing protocols
kali-tools-802-11: 802.11 (Commonly known as “Wi-Fi”)
kali-tools-bluetooth: For targeting Bluetooth devices
kali-tools-rfid: Radio-Frequency IDentification tools
kali-tools-sdr: Software-Defined Radio tools
kali-tools-voip: Voice over IP tools
kali-tools-windows-resources: Any resources which can be executed on a Windows hosts
kali-linux-labs: Environments for learning and practising on

Menu
kali-tools-information-gathering: Used for Open Source Intelligence (OSINT) & information gathering
kali-tools-vulnerability: Vulnerability assessments tools
kali-tools-web: Designed doing web applications attacks
kali-tools-database: Based around any database attacks
kali-tools-passwords: Helpful for password cracking attacks – Online & offline
kali-tools-wireless: All tools based around Wireless protocols – 802.11, Bluetooth, RFID & SDR
kali-tools-reverse-engineering: For reverse engineering binaries
kali-tools-exploitation: Commonly used for doing exploitation
kali-tools-social-engineering: Aimed for doing social engineering techniques
kali-tools-sniffing-spoofing: Any tools meant for sniffing & spoofing
kali-tools-post-exploitation: Techniques for post exploitation stage
kali-tools-forensics: Forensic tools – Live & Offline
kali-tools-reporting: Reporting tools

Others
kali-linux-large: Our previous default tools for amd64/i386 images
kali-linux-everything: Every metapackage and tool listed here
kali-desktop-live: Used during a live session when booted from the image

Desktop environments/Window managers
kali-desktop-core: Any key tools required for a GUI image
kali-desktop-e17: Enlightenment (WM)
kali-desktop-gnome: GNOME (DE)
kali-desktop-i3: i3 (WM)
kali-desktop-kde: KDE (DE)
kali-desktop-lxde: LXDE (WM)
kali-desktop-mate: MATE (DE)
kali-desktop-xfce: Xfce (WM)
