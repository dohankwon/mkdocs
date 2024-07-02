# Linux 정보 확인

아래 명령어들 중에 임의의 하나를 사용할 수 있다.

1. `cat /etc/os-release`    
    ```
    $ cat /etc/os-release 
    NAME="Ubuntu"
    VERSION="20.04.6 LTS (Focal Fossa)"
    ID=ubuntu
    ID_LIKE=debian
    PRETTY_NAME="Ubuntu 20.04.6 LTS"
    VERSION_ID="20.04"
    HOME_URL="https://www.ubuntu.com/"
    SUPPORT_URL="https://help.ubuntu.com/"
    BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
    PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
    VERSION_CODENAME=focal
    UBUNTU_CODENAME=focal
    ```

2. `grep '^VERSION' /etc/os-release` 또는 `grep -E '^(VERSION|NAME)=' /etc/os-release`
    ```
    $ grep '^VERSION' /etc/os-release
    VERSION="20.04.6 LTS (Focal Fossa)"
    VERSION_ID="20.04"
    VERSION_CODENAME=focal
    ```
    ```
    $ grep -E '^(VERSION|NAME)=' /etc/os-release
    NAME="Ubuntu"
    VERSION="20.04.6 LTS (Focal Fossa)"
    ```

3. `hostnamectl`
    ```
    $ hostnamectl
    Static hostname: COONTEC
            Icon name: computer-desktop
            Chassis: desktop
            Machine ID: 7cb3f6529f464bcea5bdb2bd25ffbaeb
            Boot ID: 7796b2105f2246bb8bea43c47edb14d5
    Operating System: Ubuntu 20.04.6 LTS
                Kernel: Linux 5.15.0-105-generic
        Architecture: x86-64
    ```

4. `uname -a`
    ```
    $ uname -a
    Linux COONTEC 5.15.0-105-generic #115~20.04.1-Ubuntu SMP Mon Apr 15 17:33:04 UTC 2024 x86_64 x86_64 x86_64 GNU/Linux
    ```
