# HA-17TRACK-Translate

[Home Assistant](https://www.home-assistant.io/) Tamplate Markdown Übersetzung für [17TRACK](https://www.17track.net/de) 

## Preview

### [Zugestellt_v1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/zugestellt_v1) | [Zugestellt_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/zugestellt_v2)
![zugestellt_v1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/zugestellt_v1.png)
![zugestellt](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/zugestellt.png)

### [In Zustellung_v1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/in_zustellung_v1) | [In Zustellung_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/in_zustellung_v2)
![in_zustellung_v1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/in_zustellung_v2.png)
![in_zustellung_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/in_zustellung_v1.png)

## Paket in Zustellung
### Passe oder Ergänze weitere Ereignisse zu deiner Paketverfolgung
v1 
```
replace("Englisch", "Deutsch.")| 
```
v2 
```
{% elif info_text == "Englisch"%}Deutsch. 
```
