# Dokumentation mit Releveanz für alle Gruppen

## Dokumente 

* [Aufgabenstellung, Ziele und Hinweise](https://github.com/ZQ-AFBB-2022/general/blob/main/docs/2022-07-10_v1.1_AFBB_ZQ_Programmierung_für_das_IoT.pdf "Aufgabenstellung ZQ IoT 2022")

## Links

* [ESP8266 Pinout Reference](https://randomnerdtutorials.com/esp8266-pinout-reference-gpios/)
* [ESP32 Pinout Reference](https://randomnerdtutorials.com/esp32-pinout-reference-gpios/)


## Zugriff auf Geräte per Web-Oberfläche

* Steckdose: http://192.168.120.82
* LED-Streifen: http://192.168.120.81


## MQTT

Momentan ist der orange Pi (192.168.120.10) als MQTT-Broker für alle Geräte konfiguriert.

* Nachrichten von allen Kanälen abbonieren: `mosquitto_sub -h 192.168.120.10 -v -t '#'`
* nur Tasmota-Kanäle abbonieren: `mosquitto_sub -h 192.168.120.10 -v -t 'tasmota/#'`
* Steckdose umschalten: `mosquitto_pub -h 192.168.120.10 -t 'tasmota/cmnd/steckdose/POWER' -m 'TOGGLE'`
* Helligkeit des LED-Streifens ändern:
   * `mosquitto_pub -h 192.168.120.10 -t 'wled/936f95' -m '10'`
   * `mosquitto_pub -h 192.168.120.10 -t 'wled/936f95' -m '255'`
* Farbe des LED-Streifens ändern:
   * `mosquitto_pub -h 192.168.120.10 -t 'wled/936f95/col' -m '#FF0000'`
   * `mosquitto_pub -h 192.168.120.10 -t 'wled/936f95/col' -m '#0000FF'`
