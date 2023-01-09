# IOT_project_dashboard
Dashboard of IOT project for IOT course of UHasselt/KULeuven using HiveMQ MQTT broker with PSOC6.

Devices for the IOT system,
- temperature and humidity sensor node
- consumer dehumidifier for home use

![Alt text](Images/IOT_project_overview.png?raw=true "Project Overview")

The dashboard can override the dehumidifier state and can set the threshold for automated use.

## Links to other documentation and repos
- github dashboard: https://github.com/VerbruggenD/IOT_project_dashboard
- github psoc: https://github.com/VerbruggenD/IOT_humidity_project
- dockerhub dashboard: https://hub.docker.com/repository/docker/dieterverbruggen/iot_dashboard/general
- google drive folder: https://drive.google.com/drive/folders/1XOHH8MmAhiO1N2XTn9_pA3xuGM-f5_lv?usp=sharing

## Dashboard documentation:
The dashboard is made with Flask in python specifically for the mqtt protocol. The bootstrap page is hosted in the application and connects with sockets to get updates and data from new mqtt messages. This application is running inside a docker container, which means there are 2 ports exposed to the outside, one for the websockets and website. The other port for encrypted mqtt messages coming from HiveMQ broker.
The requirements for the dashboard can be found in the `requirements.txt` file.

In the dashboard some sensor values are desplayed with graphs and gauges. The graphs are from the standard javascript libraries. The gauges are a lightweight version and remake from the standard javascript library. These are imported from the web instead of selfhosting these prerequisites.

The output of the dashboard is simply a few commands that control the settings and states of the dehumidifier actuator.

![Alt text](Images/flowchart_dashboard.png?raw=true "flowchart server")

The server is fully event based like seen above.

## Delivery
The docker image can be downloaded using docker hub with the following commands:
````
docker pull dieterverbruggen/iot_dashboard:latest
docker run -dp 80:80 -p 8883:8883 dieterverbruggen/iot_dashboard:latest
````
## Running the dashboard
Local only due to the lack of a free hosting service which supports the MQTT ports.
`http://localhost:80`
