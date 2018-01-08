# SolarSystemWebServer

<p>Creates a web server for monitoring and control of a pico-solar installation. Designed to run on an esp8266 nodeMCU, and has been tested on board: "NodeMCU (1.0 ESP-12E Module)".</p>
<p>At setup the infrastructure is initialized: USB serial logging, WiFi network, Network Time Protocol client, and SPIFFS file system.  Project-specific web services are then enabled including web pages for browser use.</p>
<h1>Libraries Notes</h1>
<h2>Timezone</h2>
<p>TODO: Timezone library was busted for esp8266.  The project isn't active at the moment, but ought to get fixed somehow.  My workaround:</p>
<p>- I cloned the project: https://github.com/JChristensen/Timezone.git</p>
<p>-    Then copied it to the Arduino/libraries folder</p>
<p>-    then changed #include &ltTime.h> to #include &ltTimeLib.h> in Timezone.cpp, based on info at:</p>
<p>-     https://forum.arduino.cc/index.php?topic=96891.30</p>
<h2>WiFiParams</h2>
<p>The WiFi ssid and password are needed to connect in station mode, but that's not something to publish.  So I created my own library called WiFiParams, so it is outside this project.  All it has is a single header file: WiFiParams.h.</p>
<p>To create your own WiFiParams library:</p>
<p>- Create a subfolder "WiFiParams" in your Arduino libraries folder</p>
<p>- Create a file "WiFiParams.h" there, and add the code below to the file</p>
<code>
<p>#ifndef _WIFIPARAMS_H</p>
<p>#define _WIFIPARAMS_H</p>
<p></p>
<p>//   WiFi station parameters</p>
<p>const char *ssid = &ltyour ssid>";</p>
<p>const char *password = "&ltyour password>";</p>
<p>- Update &ltyour ssid> and &ltyour password> for your network</p>
<p></p>
<p>#endif _WIFIPARAMS_H</p>
</code>
<h2>NTPClient</h2>
<p>https://github.com/arduino-libraries/NTPClient<p>
<h2>Time</h2>
<p>Using TimeLib.h, there are compilation issues with Time.h for esp8266 boards.</p>
<p>Standard Arduino, you should be able to search for it in the IDE's library manager.</p>
<p>http://playground.arduino.cc/code/time</p>

