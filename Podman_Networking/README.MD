# Networking - Podman

## Enabling REST API

```shell
sudo podman system service --time=0 \
unix:///run/podman/podman.sock

systemctl enable --now podman.socket

curl --unix-socket /tmp/podman.sock \ 
http://d/v3.0.0/libpod/images/json | jq .
```
