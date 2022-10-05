# AirQuality_UseCase_Raspi

In this project, we are analysing the air quality data with scd_30 sensor from Raspberry pi-4 in timescale database. The air quality data obtained from sensor is stored in the timescale database in windows machine using the fastAPI. 

##### Hardware_Requirements

<ol>
    <li>RaspberryPi-3/4</li>
    <li>SCD_30 Sensor</li>
</ol>

##### Set up Raspi

The raspi set up can be referred from the [link](https://github.com/cdl-mint/IndoorAirQuality_DigitalTwin_Exemplar/tree/main/physical_twin/hardware_setup).

##### script.py

The script [aquc_ec.py](https://github.com/cdl-mint/IndoorAirQuality_DigitalTwin_Exemplar/tree/main/physical_twin/hardware_setup/raspi/aquc_ec.py) contains code for getting the air quality data as well as for the energy consumption of device. The function getRaspiCurrentData() measures the energy consumption of pi which is running the airquality use case. The function sensor_data() measures air quality data from scd30 sensor and both these measurements are sent as arguments to the function post_SensorData_API(airQualityData,currentData). 

post_SensorData_API function splits the airQualityData string and gets co2, temperature and humidity values separately. Similarly the currentData string is split and the bus, shunt, load, current, and power measurements are obtained.  These values are sent as post request to the fast api deployed into server.





