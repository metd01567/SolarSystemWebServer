# SolarSystemWebServer

<p>Creates a web server for monitoring and control of a pico-solar installation. Designed to run on an esp8266 nodeMCU, and has been tested on board: "NodeMCU (1.0 ESP-12E Module".</p>
<p>At setup the infrastructure is initialized: USB serial logging, WiFi network, Network Time Protocol client, and SPIFFS file system.  Project-specific web services are then enabled including web pages for browser use.</p>
<h1>Libraries Notes</h1>
<h2>Timezone</h2>
<p>TODO: Timezone library was busted for nodeMCU.  The project isn't active at the moment, but ought to get fixed somehow.  My workaround:</p>
<p>- I cloned the project: https://github.com/JChristensen/Timezone.git</p>
<p>-    Then copied it to the Arduino/libraries folder</p>
<p>-    then changed #include <Time.h> to #incluide <TimeLib.h> in Timezone.cpp, based on info:</p>
<p>-     https://forum.arduino.cc/index.php?topic=96891.30</p>
<h2>WiFiParams</h2>
<p>The WiFi ssid and password are needed to connect in station mode, but that's not something to publish.  So I created my own library called WiFiParams, so it is outside this project.  All it has is a single header file: WiFiParams.h.</p>
<p>To create your own WiFiParams library:</p>
<p>- Create a subfolder "WiFiParams" in your Arduino libraries folder</p>
<p>- Create a file "WiFiParams.h" in the new folder</p>
<p>- Add the code below to the file</p>
<p>- Update &ltyour ssid> and &ltyour password> for your network</p>
<code>
<p>#ifndef _WIFIPARAMS_H</p>
<p>#define _WIFIPARAMS_H</p>
<p></p>
<p>//   WiFi station parameters</p>
<p>const char *ssid = &lt<your ssid>";</p>
<p>const char *password = "&ltyour password>";</p>
<p></p>
<p>#endif _WIFIPARAMS_H</p>
</code>
