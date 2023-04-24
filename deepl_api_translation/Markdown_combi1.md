type: vertical-stack
cards:
  - type: horizontal-stack
    cards:
      - show_name: true
        show_icon: true
        type: button
        tap_action:
          action: toggle
        entity: switch.update_deepl_all_translation
        name: Update DeepL Translation
        show_state: false
        icon_height: 50px
      - type: custom:mushroom-select-card
        entity: input_select.language
        fill_container: true
  - type: markdown
    content: >-
      {% if states('sensor.seventeentrack_packages_in_transit') | int == 0 %} 
      ## <center><font color="#44739e">Keine Pakete in
      Zustellung</font></center>{% else %}  ## <center> <font color="#fdd835">In
      Zustellung</font></center>{% endif %}

      ***

      {% if states('sensor.seventeentrack_packages_in_transit') == '0' %} Keine
      Pakete.   {% elif states('sensor.deepl_translation_in_transit') ==
      'unknown' %} Keine Übersetzung. {% else %}

      {% for translations in
      states.sensor.deepl_translation_in_transit.attributes.translations %}  {%
      set null = translations.text %} {% if null == "Keine" %} {% elif null ==
      "Keine\n "%} {% else %} 

      {{ translations.text }}
       
      ***
         
          {% endif %}
        {% endfor %}
      {% endif %}

      {% if states('sensor.seventeentrack_packages_delivered') | int == 0 %}  ##
      <center> <font color="#44739e">Zugestellt</font></center>{% else %}  ##
      <center> <font color="green">Zugestellt</font></center>{% endif %}

      ***

      {% if states('sensor.seventeentrack_packages_delivered') == '0' %} Keine
      Pakete.   {% elif states('sensor.deepl_translation_delivered') ==
      'unknown' %} Keine Übersetzung. {% else %}

      {% for translations in
      states.sensor.deepl_translation_delivered.attributes.translations %}  {%
      set null = translations.text %} {% if null == "Keine" %} {% elif null ==
      "Keine\n "%} {% else %} 

      {{ translations.text }}
       
      ***
         
          {% endif %}
        {% endfor %}
      {% endif %}

      {% if states('sensor.seventeentrack_packages_ready_to_be_picked_up') | int
      == 0 %}  ## <center>  <font color="#44739e">Pakete zur Abholung
      bereit</font></center> {% else %}  ## <center> <font
      color="#fdd835">Pakete zur Abholung bereit</font></center>{% endif %}

      ***

      {% if states('sensor.seventeentrack_packages_ready_to_be_picked_up') ==
      '0' %} Keine Pakete.   {% elif
      states('sensor.deepl_translation_ready_to_be_picked_up') == 'unknown' %}
      Keine Übersetzung. {% else %}

      {% for translations in
      states.sensor.deepl_translation_ready_to_be_picked_up.attributes.translations
      %}  {% set null = translations.text %} {% if null == "Keine" %} {% elif
      null == "Keine\n "%} {% else %} 

      {{ translations.text }}
       
      ***
         
          {% endif %}
        {% endfor %}
      {% endif %}
