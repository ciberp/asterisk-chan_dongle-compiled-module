# My setup

I am using RPI4 with debian Buster 10, asterisk (asterisk_16.2.1~dfsg-1+deb10u2_armhf.deb), Huawei E303S (E303Update_21.158.13.00.864_e303s-2 Huawei E303 Firmware 21.158.13.00.864 with voice support (Universal), chan_dongle.so (chan_dongle.so_wdoekes)

Works USSD, SMS, Call incoming/outgoing, but I can' t get DTMF working...


# asterisk-chan_dongle-compiled-module for raspberry pi 4 debian buster

## sources

chan_dongle.so = chan_dongle.so_haha8x

chan_dongle.so_1.1_bg111 source: https://github.com/bg111/asterisk-chan-dongle

chan_dongle.so_haha8x source: https://github.com/haha8x/asterisk-chan-dongle-16

chan_dongle.so_wdoekes source: https://github.com/wdoekes/asterisk-chan-dongle

works with asterisk 16.2.1

## compile
### dependencies
sudo apt-get install libsqlite3-dev

sudo apt-get install asterisk-dev

sudo asterisk -rvvv


### compile chan_dongle
sudo git clone https://github.com/wdoekes/asterisk-chan-dongle.git

sudo chown -R pi:pi /home/pi/asterisk-chan-dongle

cd asterisk-chan-dongle/

./bootstrap

./configure --with-astversion=16.2.1

make

## troubleshooting

https://github.com/wdoekes/asterisk-chan-dongle/issues/135

