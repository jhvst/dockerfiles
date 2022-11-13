FROM ubuntu

RUN apt update
RUN apt install git build-essential gcc g++ pkg-config make hostapd iproute2 iw -y
RUN git clone https://github.com/lakinduakash/linux-wifi-hotspot

WORKDIR /linux-wifi-hotspot
RUN git checkout v4.4.0
RUN make install-cli-only

# ENTRYPOINT [ "/linux-wifi-hotspot/src/scripts/create_ap" ]
# ENTRYPOINT [ "/linux-wifi-hotspot/src/scripts/create_ap" ]
# CMD [ "-h" ]

FROM alpine
RUN apk update
RUN apk add iw hostapd
RUN iw dev wlan0 set type __ap
RUN ip link set wlan0 master br0
RUN wpa_supplicant -c/wlan0.conf -Dnl80211,wext -iwlan0 -bbr0

interface=wlan0
bridge=br0
driver=nl80211
ssid=RPiNet
country_code=FI
hw_mode=g
channel=1
auth_algs=1
wpa=2
wpa_passphrase=test1234
wpa_key_mgmt=WPA-PSK
wpa_pairwise=TKIP
rsn_pairwise=CCMP