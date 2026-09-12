# ESP32 Spa Controller for Balboa GS100

This repository is a personal fork of [`kgstorm/Balboa-GS100-with-VL260-topside`](https://github.com/kgstorm/Balboa-GS100-with-VL260-topside).

The original project provides the ESP32/ESPHome implementation, hardware interface, protocol handling, and support for Balboa GS100 systems with VL-series topside controllers.

This fork is maintained independently for my own installation and experiemnts with changes, e.g. more robust heating-mode control, improved behavior when used from Homey and estimated power monitoring.
Ive also added filter cycle selector and detection.

For the original project documentation, hardware information, wiring, and implementation details, see the upstream repository.

## Changes in this fork

### Estimated power monitoring

A `Spa Power` sensor has been added.

Power consumption is estimated from the pump and heater states using measurements from my hot tub:

| Component      | Estimated power |
| -------------- | --------------: |
| Pump           |           396 W |
| Heater         |          2070 W |
| Pump + heater  |          2466 W |
| Neither active |             0 W |

The power sensor updates immediately when the pump or heater state changes, with a periodic refresh as a fallback.

These values are specific to my installation and should be adjusted if different hardware is used.

### Independent project identity and versioning

This fork uses its own ESPHome project identity:

```text
pathe915.esp32-spa
```

Firmware versions are maintained independently from upstream, starting from upstream version `2.8`.

For example:

```text
2.8.1
```

denotes the first fork-specific release based on upstream version 2.8.

### Firmware updates

The upstream HTTP firmware update channel has been removed.

Firmware is currently built and installed using the normal ESPHome CLI and ESPHome OTA mechanism.

Example:

```bash
esphome run esp32-spa.yaml
```

## Upstream project

This project would not exist without the work in:

[`kgstorm/Balboa-GS100-with-VL260-topside`](https://github.com/kgstorm/Balboa-GS100-with-VL260-topside)

Refer to the upstream repository for the original design, wiring, hardware documentation, protocol implementation, and project history.

## License

This fork remains distributed under the MIT License.

The original copyright and license notice from the upstream project are retained in the `LICENSE` file.
