# EVSE MQTT Add-on

**Version:** 1.0.0

Home Assistant add-on for EVSE MQTT integration using the `slespersen/evsemqtt` Docker container.

## Features

- Connects to your EVSE device via BLE
- Publishes data to an MQTT broker
- Configurable logging levels

## Installation

### Prerequisites

- Home Assistant with Supervisor enabled
- MQTT broker accessible from Home Assistant

### Adding the Add-on Repository

1. Open Home Assistant.
2. Navigate to **Settings** > **Add-ons** > **Add-on Store**.
3. Click on the three dots in the top right corner and select **Repositories**.
4. Add this repository URL: https://github.com/moryoav/evsemqtt-ha
5. Click **Add**.

### Installing the Add-on

1. Navigate to **Settings** > **Add-ons** > **Add-on Store**.
2. Find **EVSE MQTT** in the list and click on it.
3. Click **Install**.
4. After installation, navigate to the **Configuration** tab.

### Configuration

Configure the add-on by providing the required environment variables:

- **BLE_ADDRESS**: Your EVSE device's MAC address.
- **BLE_PASSWORD**: Your EVSE device's 6-digit PIN.
- **UNIT**: Measurement unit (e.g., "W" for watts).
- **MQTT_ENABLED**: Enable MQTT integration (`true` or `false`).
- **MQTT_BROKER**: Address of your MQTT broker.
- **MQTT_PORT**: Port of your MQTT broker (default is `1883`).
- **MQTT_USER**: MQTT broker username.
- **MQTT_PASSWORD**: MQTT broker password.
- **LOGGING_LEVEL**: Logging level (`DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL`).
- **RSSI**: Monitor Received Signal Strength Indicator (`true` or `false`).

Example configuration:

```json
{
"BLE_ADDRESS": "AA:BB:CC:DD:EE:FF",
"BLE_PASSWORD": "123456",
"UNIT": "W",
"MQTT_ENABLED": true,
"MQTT_BROKER": "mqtt.local",
"MQTT_PORT": 1883,
"MQTT_USER": "mqtt_user",
"MQTT_PASSWORD": "mqtt_password",
"LOGGING_LEVEL": "INFO",
"RSSI": true
}
