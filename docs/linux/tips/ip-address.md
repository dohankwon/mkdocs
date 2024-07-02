# IP 주소 확인

아래 명령어들 중에 임의의 하나를 사용할 수 있다.

## Public IP 주소

1. `curl ifconfig.me`
    ```
    $ curl ifconfig.me
    183.xx.xx.176
    ```
2. `dig +short myip.opendns.com @resolver1.opendns.com`
    ```
    $ dig +short myip.opendns.com @resolver1.opendns.com
    183.xx.xx.176
    ```

## Private IP 주소

1. `ifconfig -a`
2. `ip addr` 또는 `ip a`
3. `hostname -I | awk '{print $1}'`
4. `ip route get 1.2.3.4 | awk '{print $7}'`

