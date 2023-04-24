type: vertical-stack
cards:
  - type: markdown
    content: >-
      {% if states('sensor.seventeentrack_packages_not_found') | int == 0 %}  ##
      <center>  <font color="#44739e">Paket nicht gefunden</font></center> {%
      else %}  ## <center> <font color="red">Paket nicht
      gefunden</font></center>{% endif %}

      ***

      {% if states('sensor.seventeentrack_packages_not_found') == '0' %} Keine
      Pakete.  {% elif states('sensor.deepl_translation_not_found') == 'unknown'
      %} Keine Übersetzung. {% else %}

      {% for translations in
      states.sensor.deepl_translation_not_found.attributes.translations %}  {%
      set null = translations.text %} {% if null == "Keine" %} {% elif null ==
      "Keine\n "%} {% else %} 

      {{ translations.text }}
       
      ***
         
          {% endif %}
        {% endfor %}
      {% endif %}

      {% if states('sensor.seventeentrack_packages_expired')  | int == 0 %}  ##
      <center> <font color="#44739e">Abgelaufene Pakete</font></center> {% else
      %} ## <center> <font color="red">Abgelaufen Pakete</font></center>{% endif
      %}

      ***

      {% if states('sensor.seventeentrack_packages_expired') == '0' %} Keine
      Pakete.  {% elif states('sensor.deepl_translation_expired') == 'unknown'
      %} Keine Übersetzung. {% else %}

      {% for translations in
      states.sensor.deepl_translation_expired.attributes.translations %}  {% set
      null = translations.text %} {% if null == "Keine" %} {% elif null ==
      "Keine\n "%} {% else %} 

      {{ translations.text }}
       
      ***
         
          {% endif %}
        {% endfor %}
      {% endif %}

      {% if states('sensor.seventeentrack_packages_undelivered') | int == 0 %} 
      ## <center> <font color="#44739e">Pakete nicht zugestellt</font></center>
      {% else %}  ## <center> <font color="red">Pakete nicht
      zugestellt</font></center>{% endif %}

      ***

      {% if states('sensor.seventeentrack_packages_undelivered') == '0' %} Keine
      Pakete.  {% elif states('sensor.deepl_translation_undelivered') ==
      'unknown' %} Keine Übersetzung. {% else %}

      {% for translations in
      states.sensor.deepl_translation_undelivered.attributes.translations %}  {%
      set null = translations.text %} {% if null == "Keine" %} {% elif null ==
      "Keine\n "%} {% else %} 

      {{ translations.text }}
       
      ***
         
          {% endif %}
        {% endfor %}
      {% endif %}

      {% if states('sensor.seventeentrack_packages_returned')  | int == 0 %}  ##
      <center>  <font color="#44739e">Pakete zurückgesendet</font></center> {%
      else %}  ## <center> <font color="#fdd835">Pakete
      zurückgesendet</font></center>{% endif %}

      ***

      {% if states('sensor.seventeentrack_packages_returned') == '0' %} Keine
      Pakete.   {% elif states('sensor.deepl_translation_returned') == 'unknown'
      %} Keine Übersetzung. {% else %}

      {% for translations in
      states.sensor.deepl_translation_returned.attributes.translations %}  {%
      set null = translations.text %} {% if null == "Keine" %} {% elif null ==
      "Keine\n "%} {% else %} 

      {{ translations.text }}
       
      ***
         
          {% endif %}
        {% endfor %}
      {% endif %}
