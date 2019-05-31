# homeassistant-infinitude
Home Assistant custom component for controlling Carrier Infinity Touch thermostats through an [Infinitude](https://github.com/nebulous/infinitude) proxy server.

# Installation Instructions

## Install Manually

1. Create a `custom_components` directory within your Home Assistant `config` directory if it does not already exist.

2. [Download this repository](https://github.com/MizterB/homeassistant-infinitude/archive/master.zip).

3. Copy `custom_components/infinitude` from the repository into Home Assistant's `custom_components` directory.

4. Follow the configuration instructions.

## Install with custom_updater
_These instructions still need to be validated_

This custom component can be integrated into [custom_updater](https://github.com/custom-components/custom_updater), so you can track future updates.  

As this is not included in the default custom component list, add the following to your `configuration.yaml`:

```yaml
custom_updater:
  component_urls:
    - https://raw.githubusercontent.com/MizterB/homeassistant-infinitude/master/custom_components.json
```

# Configuration
Add the following to your `configuration.yaml`:
```yaml
climate:
  - platform: infinitude
    host: <infinitude_hostname_or_ip>
    port: <optional, defaults to 3000>
    zone_names:
      - Custom Name 1
      - Custom Name 2
      - ...
```
Custom zone names are optional, and are applied in ascending order (zones 1-8).  If not provided, the zone name is retrieved from the thermostat itself.
## Changelog
*0.4*
- Added manifest.json
- Fixed temperature setting reversal while on Auto mode(thanks @ccalica!)

*0.3*
- Safely handle updates of values that might not exist on all thermostats
- Provide ability to override zone names

*0.2*
- Updated constants to be compatible with HA .89

*0.1*
- Initial release