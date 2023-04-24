# HA-17TRACK-Translate

[Home Assistant](https://www.home-assistant.io/) Tamplate Markdown Paket Status Übersetzung für [17TRACK Integration](https://www.home-assistant.io/integrations/seventeentrack)

## Screenshot
![zugestellt](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/preview.gif)

#### Passe oder Ergänze weitere Ereignisse zu deiner Paketverfolgung
##### [Zugestellt_v1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/zugestellt_v1#L7) | [Zugestellt_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/zugestellt_v2#L14) | [In Zustellung_v2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/in_zustellung_v2#L24)
```
{% elif info_text == "Englisch"%}Überzetzung. 
```

### [DeepL](https://www.deepl.com/) API Translation
##### Automatische Erkennung und Übersetzung. 
#### Benötigt [DeepL API Free Konto](https://www.deepl.com/de/pro-api?cta=checkout-pro)
### [DeelP API](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp_api_translation/)
##### [Markdown DeepL 1](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp_api_translation/markdown_combi1.md) | [Markdown DeepL 2](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp_api_translation/markdown_combi2.md) | [Packages](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp_api_translation/deepl_translation_packages.yaml)  
##### Ersetze die [Authentifizierungsschlüssel](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/deelp_api_translation/deepl_translation_packages.yaml#L134)  für die DeepL-API in secrets.yaml
```
Authorization: !secret deepl_apikey #Authentifizierungsschlüssel für die DeepL-API 
```
### Custom
```
# Tracking-Link dhl.de öffnet Ihre DHL Sendungsnummer.
([{{ package.tracking_number }}](https://www.dhl.de/de/privatkunden/pakete-empfangen/verfolgen.html?piececode={{ package.tracking_number }}))

# Zeit Format 09.02.2023 10:20
am {{ as_timestamp(package.timestamp) | timestamp_custom('%d.%m.%Y %H:%M') }} Uhr.

am ['timestamp'].strftime('%d.%m.%Y %H:%M')

# Paket Status Farbwechsel
{% if states('sensor.seventeentrack_packages_in_transit') | int == 0 %} 
## <center><font color="#44739e">Keine Pakete in Zustellung</font></center>{% else %}  
## <center> <font color="#fdd835">In Zustellung</font></center>{% endif %}

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

![Weiterer Paketstatus](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/other.png)

![Kombi DeepL](https://github.com/Morpheus2018/HA-17TRACK-Translate/blob/main/png/combi_deepl.png)