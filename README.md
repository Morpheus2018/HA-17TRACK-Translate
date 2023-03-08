# HA-17TRACK-Translate

[Home Assistant](https://www.home-assistant.io/) Tamplate Markdown Paket Status Übersetzung für [17TRACK](https://www.home-assistant.io/integrations/seventeentrack) Integration

## Preview

### [Zugestellt_v1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/zugestellt_v1) | [Zugestellt_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/zugestellt_v2)
![zugestellt_v1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/zugestellt_v1.png)
![zugestellt](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/zugestellt.png)

### [In Zustellung_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/in_zustellung_v2) 
![in_zustellung_v1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/in_zustellung_v2.png)
![in_zustellung_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/in_zustellung_v1.png)

### Paket in Zustellung
#### Passe oder Ergänze weitere Ereignisse zu deiner Paketverfolgung

### [In Zustellung_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/in_zustellung_v2#L17) | [Zugestellt](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/zugestellt_v2#L10)
```
{% elif info_text == "Englisch"%}Deutsch. 
```

### DeepL API Translation
#### Automatische Erkennung und Übersetzung. 
#### [Zugestellt DeepL](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/zugestellt_deepl) 
#### [In Zustellung DeepL](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/in_zustellung_deepl) 
#### [Packages](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/deepl_translation.yaml) 

### Voraussetzung [DeepL-Konto](https://www.deepl.com/) 
#### Erstellen Sie ein neues [DeepL API Free Konto](https://www.deepl.com/de/pro-api?cta=checkout-pro) 
#### Ersetze die Authentifizierungsschlüssel für die DeepL-API in [Packages](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/deepl_translation.yaml#L24) 
```
Authorization: !secret deepl_apikey #Authentifizierungsschlüssel für der DeepL-API 
```

### [DeelP API](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/combi_deepl)
![Kombi DeepL](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/combi_deepl.png)

### Custom
```
# Tracking-Link dhl.de öffnet Ihre DHL Sendungsnummer.
([{{ package.tracking_number }}](https://www.dhl.de/de/privatkunden/pakete-empfangen/verfolgen.html?piececode={{ package.tracking_number }}))

# Zeit Format 09.02.2023 10:20
am {{ as_timestamp(package.timestamp) | timestamp_custom('%d.%m.%Y %H:%M') }} Uhr.

# Farbwechsel bei Status In Zustellung
{% if states('sensor.seventeentrack_packages_in_transit') == '1' %}
## <center>  <font color="#fdd835">In Zustellung</font></center>
{% else %}
## <center> <font color="#44739e">Keine Pakete in Zustellung</font></center>
{% endif %}
```
![Coustom URL Color](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/custom_url_color.png)
