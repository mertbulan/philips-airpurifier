[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg?style=for-the-badge)](https://github.com/custom-components/hacs)

This is a `Local Push` integration for Philips airpurifiers.
Currently only encrypted-CoAP is implemented.

## Usage:
```yaml
fan:
  platform: philips_airpurifier
  host: 192.168.0.17
  model: ac4236
```

## Configuration variables:
Field | Value | Necessity | Description
--- | --- | --- | ---
platform | `philips_airpurifier` | *Required* | The platform name.
host | 192.168.0.17 | *Required* | IP address of the Purifier.
model | ac4236 | *Required* | Model of the Purifier.
name | Philips Air Purifier | Optional | Name of the Fan.
***


## Supported models:

- AC1214
- AC2729
- AC2889
- AC3858
- AC4236

## Is your model not supported yet?

You can help to get us there.

Please open an issue and provide the raw status-data for each combination of modes and speeds for your model.

To aquire those information please follow these steps:

### Prepare the environment

```sh
git clone https://github.com/betaboon/philips-airpurifier.git
cd philips-airpurifier
source aioairctrl-shell.sh
```

### Aquire raw status-data

- Use the philips-app to activate a mode or speed
- run the following command to aquire the raw data (still in the venv)

```sh
aioairctrl --host $DEVICE_IP status --json
```

## Debugging

To aquire debug-logs, add the following to your `configuration.yaml`:

```yaml
logger:
  logs:
    custom_components.philips_airpurifier: debug
```

logs should now be available in `home-assistant.log`
