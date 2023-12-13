# Rough Hackathon effort to dynamically create sensor data, send to microshift, and skupper call OCP micro service



### simulators

Note: much of this is taken from  
https://github.com/joshdreagan/iot-demo

- You can run the Python script to simulate device telemetry being sent to the AMQ Broker

  ```
  python simulators/iot/pumpjack/sim.py --location-id field-01 --rig-id pumpjack-01 --broker-username admin --broker-password admin --telemetry-topic 'iot.telemetry' --telemetry-frequency 1 --buffer-timeout 10000 --verbose 'tcp://localhost:1883'
  ```

  - You can run `python simulators/iot/pumpjack/sim.py --help` for more details/options 

### edge-processor

- json output format for remote service validation  
  {"locationId": "field-01", "rigId": "pumpjack-01", "time": 1701184419877, "source": "pumpjack", "type": "heartbeat", "metric": "voltage", "value": 380}