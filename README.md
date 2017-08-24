# BoseSoundtouch
use Bose Soundtouch without the app for privacy reasons

Initial setup without App

Setting up Bose Soundtouch Devices needs an (Android/Iphone) app.
If you worry about privacy you could use the following steps instead.

1) unbox the device and switch it on ( if you already configured your device do a firmware reset => Press and hold the "system's 1 and both Volume buttons" for 10 seconds)

2) look for an unsecured wifi (eg "Bose ST 10")

3) use Linux to connect to this network 

4) connect to the Soundtouch with "netcat 192.0.2.1 17000"

5) use the following commands to configure your WIFI connection

```async_responses on
network wifi profiles add <SSID> wpa_or_wpa2 <yourpassphrase>
network mode auto
sys reboot
```

Remember: this is an unencrypted connection. But... its also an unencrypted connection if you use the App for initial setup.

Example output:

>async_responses on
Done

->network wifi profiles add Speedport wpa_or_wpa2 mysecret
WiFi Profiles Add requested. Wait for asynchronous response (MUST run 'async_responses on')
->OK
->
<?xml version="1.0" encoding="UTF-8" ?>
<WiFiProfileStatus operation="WIFI_ADD_SUCCEEDED" status="ADD_PROFILE_SUCCEEDED">
    <profiles>
        <profile SSID="Speedport" priority="1" security="wpa_or_wpa2" passphrase="x6xixxxxu7kOOoT7id+Q==" wepKey="+MOENxxx9Q==" encrypted="true" lastConnected="1502033186" />
    </profiles>
    <stationStats rssi_dBm="-60" linkSpeed_Mbps="52" noise_dBm="9999" frequency_kHz="2452" width_kHz="20" averageRssi_dBm="-61" txGood_packets="11" txBad_packets="0" rxGood_packets="13" tryAuthenticate="1" tryAssociate="1" connected="1" disconnected="0" handshakeFailed="0" ssidTempDisabled="0" />
</WiFiProfileStatus>

->network mode auto
mode set to auto
->OK
->
->sys reboot
Rebooting system
->OK


6) use https://github.com/CharlesBlonde/libsoundtouch to assign the buttons
