# Spike: Display key-value stored in Consul in Grafana dashboard

Spike to see if we can display the key-value stored in Consul through the Grafana dashboard

## Component Custodian(s)

Beth Skurrie beth.skurrie@rea-group.com
SPoG team
[Sean Johnson](sean.johnson@iag.com.au)

## Local Development

## Prerequisites

  * Install docker-machine
  * Ports 3000,80,8500,55,8083,8086 to be available
  * If not, change the port bindings in docker-compose file

## Development

  * docker-compose up -d
  * Open [Consul](http://<host-ip>:8500/ui/#/dc1/services)
  * Open [InfluxDB](http://<host-ip>:8083/)
  * Open [Grafana](http://<host-ip>:3000/)
    * admin/admin is the default user credentials

### Testing

#### Add data to InfluxDB

  * Open InfluxDB and select the <code>digital_apps_health</code> database
  * Select writedata
    * Copy content from data_influxdb.txt

### Display data in Grafana

  * Open Grafana
  * Login with default credentials
  * Add InfluxDB details
    * Add datasource
    * ![InfluxDB Configurations](/screenshots/influxdb-config.png?raw=true "InfluxDB Configurations")
  * Import the dashboards from exported json at grafana_exports folder
    * Import ```spog.json``` file
    * Import ```info.json``` file
    * Import ```kana.json``` file
      * ![Grafana Import](/screenshots/grafana-import.jpg?raw=true "Grafana Import")

### Architecture

[SPoG Architecure](https://confluence.iag.com.au/display/CON/Architecture)
