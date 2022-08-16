# Networking - Podman

## Enabling REST API

### Socket

```shell
sudo podman system service --time=0 \
unix:///run/podman/podman.sock

systemctl enable --now podman.socket

curl --unix-socket /tmp/podman.sock \ 
http://d/v3.0.0/libpod/images/json | jq .
```

### Host

```shell

sudo podman system service --time=0 tcp:localhost:7181

curl http://localhost:7181/v3.0.0/libpod/images/json | jq .




sudo podman system service --time=0 tcp::7181

netstat -tnlp

```
