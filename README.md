# IOT_project_dashboard
Dashboard of IOT project for IOT course of UHasselt/KULeuven using HiveMQ MQTT broker with PSOC6.

Devices for the IOT system,
- temperature and humidity sensor node
- consumer dehumidifier for home use

At later stage maybe a station using an off the shelf arduino just to test the concept.

## Delivery
The docker image can be downloaded using docker hub with the following commands:
````
docker pull dieterverbruggen/iot_dashboard:latest
docker run -dp 80:80 -p 8883:8883 dieterverbruggen/iot_dashboard:latest
````
## Running the dashboard
Local only due to the lack of a free hosting service which supports the MQTT ports.
http://localhost:80
