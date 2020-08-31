# Timepicker Buttons Panel for Grafana
[![license](https://img.shields.io/github/license/mashape/apistatus.svg)]()

A Grafana panel which allows you to create a list of buttons which set specific times (retrieved from a datasource) on the dashboard's timepicker when clicked.

![Panel Screenshot](https://i.imgur.com/91PSO4b.png)

--------

## Installation

```bash
sudo service grafana-server stop
cd /var/lib/grafana/plugins
sudo git clone https://github.com/WilliamVenner/grafana-timepicker-buttons
sudo mv grafana-timepicker-buttons williamvenner-timepickerbuttons-panel
sudo chown grafana:grafana williamvenner-timepickerbuttons-panel -R
sudo chmod 774 williamvenner-timepickerbuttons-panel -R
sudo service grafana-server start
```

--------

## Usage

All dates and times should use UTC.

The data returned from the datasource must have the following columns:

| Column          | Description                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **button_text** | **Required**: What the text inside the button will say.                                                                                                                                            |
| **time_from**   | **Required**: A UNIX Timestamp or [moment.js](https://momentjs.com/) compatible date format. This will set the "From" part of the time range.                                                   |
| **time_to**     | _Optional:_ A UNIX Timestamp or [moment.js](https://momentjs.com/) compatible date format. This will set the "To" part of the time range. If this is not supplied, it will default to `now`. |

**Don't forget to change "Format as" from "Time series" to "Table."**

![Example Screenshot](https://i.imgur.com/YBisZ7L.png)

--------

**Credit**

Logo made by [DinosoftLabs](https://flaticon.com/authors/dinosoftlabs) on [www.flaticon.com](https://flaticon.com)