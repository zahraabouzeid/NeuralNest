## Run Linux on Windows
Check the tutorial [here](https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package) or see this [video](https://youtu.be/AfVH54edAHU?si=fN99ApcLmZwQLTYt).

**List all WSLs**
```bash
wsl --list --verbose
```

**Shutdown all WSLs**
```bash
wsl --shutdown 
wsl -t kali-linux
```

**RDP**
```bash
 sudo service xrdp start
 ip add
```

**Kex**
```bash
sudo apt install kali-win-kex
kex
```
**Issues**
Stuck on setting up libc:amd64 can be solved using the following:
```bash
sudo mv /usr/sbin/telinit /usr/sbin/telinit.bak 
sudo ln -s /usr/bin/true /usr/sbin/telinit
```

#### Login as root
```bash
wsl -d kali-linux -u root
```
## Tools
- `ipcalc` to calculate network informations based on an IP and subnetmask.