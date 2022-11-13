# linux-wifi-hotspot

Unlike most containers this needs privilege escalations. `podman` does not work, `docker` must be used.

1. sudo docker build . -t linux-wifi-hotspot
2. sudo docker run \
    -it \
    --net=host \
    --cap-add=NET_ADMIN \
    --cap-add=SYS_ADMIN \
    alpine
    linux-wifi-hotspot \
    -m bridge \
    wlan0 enabcm6e4ei0 \
    MyAccessPoint MyPassPhrase
4. dhcrelay -d 192.168.17.1