# HA-17TRACK-Translate

[Home Assistant](https://www.home-assistant.io/) Tamplate Markdown Paket Status Übersetzung für [17TRACK](https://www.home-assistant.io/integrations/seventeentrack) Integration

## Preview
![zugestellt](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/preview.gif)

#### Passe oder Ergänze weitere Ereignisse zu deiner Paketverfolgung
##### [Zugestellt_v1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/zugestellt_v1#L7) | [Zugestellt_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/zugestellt_v2#L10) | [In Zustellung_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/in_zustellung_v2#L17)
```
{% elif info_text == "Englisch"%}Überzetzung. 
```

### [DeepL](https://www.deepl.com/) API Translation
#### Voraussetzung, erstellen Sie ein [DeepL API Free Konto](https://www.deepl.com/de/pro-api?cta=checkout-pro)
##### Automatische Erkennung und Übersetzung. 
##### [Zugestellt DeepL](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/zugestellt_deepl) | [In Zustellung DeepL](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/in_zustellung_deepl) | [Packages](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/deepl_translation.yaml) 
##### Ersetze die Authentifizierungsschlüssel für die DeepL-API in [Packages](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/deepl_translation.yaml#L24) 
```
Authorization: !secret deepl_apikey #Authentifizierungsschlüssel für die DeepL-API 
```
### [DeelP API](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/combi_deepl)
![Kombi DeepL](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/combi_deepl.png)

### [Custom](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/custom_url_color)
```
# Tracking-Link dhl.de öffnet Ihre DHL Sendungsnummer.
([{{ package.tracking_number }}](https://www.dhl.de/de/privatkunden/pakete-empfangen/verfolgen.html?piececode={{ package.tracking_number }}))

# Zeit Format 09.02.2023 10:20
am {{ as_timestamp(package.timestamp) | timestamp_custom('%d.%m.%Y %H:%M') }} Uhr.

# Paket Status Farbwechsel
{% if states('sensor.seventeentrack_packages_in_transit') == '1' %}
## <center>  <font color="#fdd835">In Zustellung</font></center>
{% else %}
## <center> <font color="#44739e">Keine Pakete in Zustellung</font></center>
{% endif %}

# Ziel Sprache Auswahl
target_lang={{ states.input_select.language.state }}

input_select:
      language:
        name: Sprache
        options:
          - EN
          - DE
          - ES
          - FR
        initial: DE
        icon: mdi:earth
```
![Coustom URL Color](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/custom_url_color.png)

### [Weiterer Paketstatus](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp.api_translation/deepl_translation_other)
* Not found   - Funktioniert (Attribute status)
* Expired     - Nicht Getestet (Attribute status)
* Pick up     - Nicht Getestet (Attribute status)
* Undelivered - Nicht Getestet (Attribute status)
* Alert       - Nicht Getestet (Attribute status)

![Weiterer Paketstatus](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/other.png)
