# Communication

## Description of the context

We will discuss and evaluate the best way to exchange data between probe and mobile application.

the nature of the data stream is:
  * raw images are streamed to the mobile application with 10 - 15 FPS

  * probe battery status is regularly sent to mobile application

  * user acquisition settings changes on mobile application have to be dispatch to the probe ie frequency change, TGC change ...

  * (optionnal) user triggered events on probe ie screen capture


## Existing solutions

|  | Bandwidth | pairing | security | robustness | range | protocol | maturity of technology | autonomy / energy consumption | real-time ? | cost | transfer frequency spectrum | comments |
|---|---|----|---|---|---|---|---|---|---|---|---|---|
| USB 2.0 OTG  communication | 280 Mb/s | instantaneous | / | - wire robustness | length of the cable | TCP, Series, audio protocol - check android compatibility | battle tested | / | yes | 1 $ | / | wired, reglementation ? |
|Wifi - infrastructure | very unstable | manual the first time. very complex for the probe to connect | SSL / TLS - standard | very unstable | 200m | TCP | battle tested | 10+ hours | yes | < 10$ | 2,4 GHz |  |
| Wifi - point to point - websocket | 100 Mb/s theorical | manual, automatic with tag NFC ? - https://stackoverflow.com/questions/2140133/how-and-what-to-set-to-android-wificonfiguration-presharedkey-to-connect-to-the | SSL / TLS - standard | resilient | 200m | TCP | battle tested | 10+ hours | yes - GoPro stream to mobile app | < 10$ | 2,4GHz | no sharing, no internet connection |
| Bluetooth LE | on field - 800kb/s | almost automatic | security 3 levels -  LMP protocol | medium | 30m | Series, LE, AD2P, see incomming video protocol| battle tested | see headset autonomy | ok | <10$ | 2,4GHz | |
| Bluetooth  Classic 3.0 - SPP |on field - 800kb/s | pairing delay ~ 20 seconds | security 3 levels -  LMP protocol | medium | 30m | Series, LE, AD2P, see incomming video protocol | unknown |  see headset autonomy | ok | < 10 $| 2,4 GHz| |
| Bluetooth Classic 3.0 - High speed | theorically - 24 Mb/s | pairing delay ~ 20 seconds | security 3 levels -  LMP protocol | medium | 30m| Series, LE, AD2P, see incomming video protocol| battle tested |  see headset autonomy  | ok | < 10$ | 2,4 GHz | to be challenged, no apparent use |
| Bluetooth 5.0 | on field - 1,4Mb/s |  almost automatic | security 3 levels -  LMP protocol | medium | 30m | Series, LE, AD2P, see incomming video protocol| battle tested |  see headset autonomy | ok | < 10$ | 2,4 GHz | / |


We could explore also home made radio communication with dongle on smartphone.

## What is done on similar devices
 **GE Healthcare VScan** probe is wired to the smartphone

 **Clarius Imaging** supports devices with Wi-Fi 802.11n and BLE 4.1

 **Philips Lumify** probe is wired to the smartphone

 **Butterfly IQ** probe is wired to the smartphone

## Discussion

* investigate Wifi pairing
* implementation software for TCP protocol on Wifi
* implementation software to stream with TCP protocol on USB
