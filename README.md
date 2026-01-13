
# AHT10 Erweiterung für micro:bit (MakeCode)

Eine einfache MakeCode-Erweiterung für den AHT10 (Temperatur & Luftfeuchtigkeit) über I²C.

## Verdrahtung
- AHT10 VCC → 3.3V (kein 5V!)
- AHT10 GND → GND
- AHT10 SDA → P20 (SDA)
- AHT10 SCL → P19 (SCL)
- Standardadresse: 0x38

## Blöcke
- **AHT10 initialisieren an Adresse …**
- **AHT10 Luftfeuchtigkeit (%) an Adresse …**
- **AHT10 Temperatur (°C) an Adresse …**
- **AHT10 Temperatur (°F) an Adresse …**
- **AHT10 Soft-Reset an Adresse …** (optional bei Problemen)

## Beispiel (Blöcke)
- Im `Beim Start`-Block: `AHT10 initialisieren (0x38)`
- Im `Dauerhaft`-Block:
  - `zeige Zahl (AHT10 Temperatur (°C))`
  - `zeige Zahl (AHT10 Luftfeuchtigkeit (%))`

## Beispiel (JavaScript)
```ts
AHT10.initialize()
basic.forever(function () {
    const t = AHT10.temperatureC()
    const h = AHT10.humidity()
    basic.showNumber(Math.round(t))
    basic.pause(500)
    basic.showNumber(Math.round(h))
    basic.pause(500)
})
``
