<img src="https://raw.githubusercontent.com/barloew/homekit-adjustable-bed/main/custom_components/homekit_adjustable_bed/brand/icon.png" alt="HomeKit Adjustable Bed" width="96" align="right">

# HomeKit Adjustable Bed

[![Release][release-badge]][release-url]
[![HACS][hacs-badge]][hacs-url]
[![Validate][validate-badge]][validate-url]

Exposes an Adjustable Bed as a single HomeKit accessory with exact positions.

Publishes a bed from [Adjustable Bed][adjustable-bed] to the Apple Home app as one accessory with its own pairing code. Bed sections, presets, massage, lights and climate appear as named sliders and buttons in a single tile.

## Features

- **Exact positions:** a slider set to 40% moves the section to 40%, with live feedback. The HomeKit Bridge cannot expose Adjustable Bed's position entities.
- **One tile per bed:** all controls in one accessory, each with its own name in the Home app.
- **Motion queue:** sections move one after another, slider drags are debounced and Stop clears the queue.
- **Automatic setup:** controls follow Adjustable Bed's own detection for the bed type, without duplicates.
- **Safe defaults:** actions such as saving memories or factory reset are off by default, as HomeKit asks for no confirmation.
- **Stable in HomeKit:** adding or removing controls keeps names, scenes and automations in the Home app intact.
- **Combined beds:** a parent bed gets controls for both sides; each side can also be its own accessory.

Available in English and Dutch.

## Requirements

- Home Assistant 2026.9 or later
- <!-- adjustable-bed-version -->[Adjustable Bed](https://github.com/kristofferR/ha-adjustable-bed) v4 with your bed set up (checked against v5.0.0, see [Supported beds](docs/SUPPORTED_BEDS.md))<!-- /adjustable-bed-version -->
- A free TCP port per bed (default 21070), reachable from your Apple home hub

## Installation

### HACS

[![Open in HACS][my-ha-badge]][my-ha-url]

Or add it manually:

1. In HACS, open the menu and select **Custom repositories**.
2. Add `https://github.com/barloew/homekit-adjustable-bed` with category **Integration**.
3. Download **HomeKit Adjustable Bed** and restart Home Assistant.

### Manual

Copy `custom_components/homekit_adjustable_bed` from the [latest release][release-url] to your `config/custom_components` folder and restart Home Assistant.

## Configuration

1. Go to **Settings → Devices & services → Add integration** and select **HomeKit Adjustable Bed**.
2. Select the Adjustable Bed device and a port, review the controls and submit.
3. Open the **Pair HomeKit Adjustable Bed** notification and scan the QR code with the Home app.
4. If you also use the HomeKit Bridge, exclude the bed's entities there to avoid duplicate tiles.

## Documentation

- [Configuration](docs/CONFIGURATION.md): setup and options, naming, layout, pairing
- [Detection](docs/DETECTION.md): how bed entities map to HomeKit controls
- [Supported beds](docs/SUPPORTED_BEDS.md)
- [Home app behavior](docs/HOME_APP.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Development](docs/DEVELOPMENT.md): toolchain, tests and staying in sync with Adjustable Bed
- [Changelog](CHANGELOG.md)

## Status

Used daily with a Jensen JMC400, as single and combined beds. Other bed types are covered by tests against every Adjustable Bed release. Reports from owners of other beds are welcome.

## License

[MIT](LICENSE). Not affiliated with Apple.

[release-badge]: https://img.shields.io/github/v/release/barloew/homekit-adjustable-bed
[release-url]: https://github.com/barloew/homekit-adjustable-bed/releases
[hacs-badge]: https://img.shields.io/badge/HACS-Custom-41BDF5.svg
[hacs-url]: https://github.com/hacs/integration
[validate-badge]: https://github.com/barloew/homekit-adjustable-bed/actions/workflows/validate.yml/badge.svg
[validate-url]: https://github.com/barloew/homekit-adjustable-bed/actions/workflows/validate.yml
[my-ha-badge]: https://my.home-assistant.io/badges/hacs_repository.svg
[my-ha-url]: https://my.home-assistant.io/redirect/hacs_repository/?owner=barloew&repository=homekit-adjustable-bed&category=integration
[adjustable-bed]: https://github.com/kristofferR/ha-adjustable-bed
