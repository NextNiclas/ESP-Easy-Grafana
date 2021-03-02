# Simple ESP-Easy Docker Stack

## Container

- Eclipse Mosquitto 2.0.7
- NodeRED 1.2.9
- InfluxDB 1.8.4
- Grafana 7.4.3

Uses Influx 1.8.4 and not 2.x for compatibility reasons with NodeRed InfluxDB node.

## Getting Started

### Start Stack

Run using docker-compose: `docker-compose up -d`

### Connect ESP Easy to Eclipse Mosquitto

1. Navigate to ESP Easy Dashboard
2. Add `Home Assistant (openHAB) MQTT` Controller
3. Enter the IP of your Host as `Controller IP`
4. Check `Enabled`

### Persist Measurements in InfluxDB using NodeRED Flow

1. Open NodeRED `http://<YourHost>:1880`
2. Click Burger Menu on right top -> Import
3. Select `persist_mqtt_to_influxdb.json` from `docs/node_red_flows`and click Import
4. Deploy flow: Click Deploy

### View Metrics on Grafana

1. Open Grafana `http://<YourHost>:1880` (Default credentials admin:admin)
2. Add Datasource: InfluxDB

- **URL:** influxdb:8086
- **Database:** influxdb
- **User:** influxdb
- **Password**: influxdb
- Save & Test

3. Import Dashboard: Upload JSON file, select `bme280.json` from `docs/grafana_dashboards` and click `Load`
