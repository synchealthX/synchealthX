👋 TIPS

Home Assistant - Inversor - Kostal PIKO 4.6-2 MP plus 

Recursos: https://github.com/danieldotnl/ha-multiscrape#debug-logging

#COMO
Instalar HACS, añadir repositorio multiscrape con configuracion en carpeta X
Añadir la siguiente configuracion en /config/ ver directorio.
#


# Kostal inverter LUCI Pico
multiscrape:
  - resource: http://192.168.2.11/measurements.xml
    scan_interval: 60
    parser: lxml
    sensor:
      - unique_id: kostal_ac_power
        name: "AC Power"
        select: "measurement[type='AC_Power']"
        attribute: "value"
        unit_of_measurement: "W"
        on_error:
          value: "default"
          default: 0.0
      - unique_id: kostal_ac_power_fast
        name: "AC Power Fast"
        select: "measurement[type='AC_Power_fast']"
        attribute: "value"
        unit_of_measurement: "W"
        on_error:
          value: "default"
          default: 0.0
      - unique_id: kostal_ac_voltage
        name: "AC Voltage"
        select: "measurement[type='AC_Voltage']"
        attribute: "value"
        unit_of_measurement: "V"
        on_error:
          value: "default"
          default: 0.0
      - unique_id: kostal_ac_current
        name: "AC Current"
        select: "measurement[type='AC_Current']"
        attribute: "value"
        unit_of_measurement: "A"
        on_error:
          value: "default"
          default: 0.0
      - unique_id: kostal_ac_frequency
        name: "AC Frequency"
        select: "measurement[type='AC_Frequency']"
        attribute: "value"
        unit_of_measurement: "Hz"
      - unique_id: kostal_dc_voltage1
        name: "DC Voltage 1"
        select: "measurement[type='DC_Voltage1']"
        attribute: "value"
        unit_of_measurement: "V"
        on_error:
          value: "default"
          default: 0.0
      - unique_id: kostal_dc_voltage2
        name: "DC Voltage 2"
        select: "measurement[type='DC_Voltage2']"
        attribute: "value"
        unit_of_measurement: "V"
        on_error:
          value: "default"
          default: 0.0
      - unique_id: kostal_dc_current1
        name: "DC Current 1"
        select: "measurement[type='DC_Current1']"
        attribute: "value"
        unit_of_measurement: "A"
        on_error:
          value: "default"
          default: 0.0
      - unique_id: kostal_dc_current2
        name: "DC Current 2"
        select: "measurement[type='DC_Current2']"
        attribute: "value"
        unit_of_measurement: "A"
        on_error:
          value: "default"
          default: 0.0
      - unique_id: kostal_link_voltage
        name: "Link Voltage"
        select: "measurement[type='LINK_Voltage']"
        attribute: "value"
        unit_of_measurement: "V"
        on_error:
          value: "default"
          default: 0.0
      - unique_id: kostal_derating
        name: "Derating"
        select: "measurement[type='Derating']"
        attribute: "value"
        unit_of_measurement: "%"
      - unique_id: kostal_dc_power1
        name: "DC Power 1"
        select: "measurement[type='DC_Power1']"
        attribute: "value"
        unit_of_measurement: "W"
        on_error:
          value: "default"
      - unique_id: kostal_dc_power2
        name: "DC Power 2"
        select: "measurement[type='DC_Power2']"
        attribute: "value"
        unit_of_measurement: "W"
        on_error:
          value: "default"
      - unique_id: kostal_dc_power_total
        name: "DC Power Total"
        select: "measurement[type='DC_Power Total']"
        attribute: "value"
        unit_of_measurement: "W"
        on_error:
          value: "default"
      - unique_id: kostal_temp
        name: "Temperatura"
        select: "measurement[type='Temp']"
        attribute: "value"
        unit_of_measurement: "ºC"
        on_error:
          value: "default"
      - unique_id: kostal_GridPower
        name: "GridPower"
        select: "measurement[type='GridPower']"
        attribute: "value"
        unit_of_measurement: "W"
        on_error:
          value: "default"
      - unique_id: kostal_GridConsumedPower
        name: "GridConsumedPower"
        select: "measurement[type='GridConsumedPower']"
        attribute: "value"
        unit_of_measurement: "W"
        on_error:
          value: "default"
      - unique_id: kostal_GridInjectedPower
        name: "GridInjectedPower"
        select: "measurement[type='GridInjectedPower']"
        attribute: "value"
        unit_of_measurement: "W"
        on_error:
          value: "default"
      - unique_id: kostal_OwnConsumedPower
        name: "OwnConsumedPower"
        select: "measurement[type='OwnConsumedPower']"
        attribute: "value"
        unit_of_measurement: "W"
        on_error:
          value: "default"

