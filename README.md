# Dokumentation mit Releveanz für alle Gruppen

## Dokumente 

* [Aufgabenstellung, Ziele und Hinweise](https://github.com/ZQ-AFBB-2023/general/blob/main/docs/2023-06-11_v1.2_AFBB_ZQ_Programmierung_f%C3%BCr_das_IoT.pdf "Aufgabenstellung ZQ IoT 2023")

## Links

* [ESP8266 Pinout Reference](https://randomnerdtutorials.com/esp8266-pinout-reference-gpios/)
* [ESP32 Pinout Reference](https://randomnerdtutorials.com/esp32-pinout-reference-gpios/)


## Zugriff auf Geräte per Web-Oberfläche

* LED-Streifen: http://192.168.120.81


## MQTT

Momentan ist der orange Pi (192.168.120.10) als MQTT-Broker für alle Geräte konfiguriert.

* Nachrichten von allen Kanälen abbonieren: `mosquitto_sub -h 192.168.120.10 -v -t '#'`
* Helligkeit des LED-Streifens ändern:
   * `mosquitto_pub -h 192.168.120.10 -t 'wled/936f95' -m '10'`
   * `mosquitto_pub -h 192.168.120.10 -t 'wled/936f95' -m '255'`
* Farbe des LED-Streifens ändern:
   * `mosquitto_pub -h 192.168.120.10 -t 'wled/936f95/col' -m '#FF0000'`
   * `mosquitto_pub -h 192.168.120.10 -t 'wled/936f95/col' -m '#0000FF'`
