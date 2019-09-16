# mqtt_matlab_interface
MATLAB interface to MQTT, based on the [Paho Java client](https://www.eclipse.org/paho/clients/java/)
Based on: https://github.com/gnotomista/mqtt_matlab_interface
Bare bones implementation which allows to connect to an mqtt broker (e.g. https://mosquitto.org/), publish and subscribe to multiple topics.

To run mosquitto:
1. To install mosquitto on MacOS using homebrew (https://brew.sh/), run: `brew install mosquitto`
3. You can make changes to the configuration by editing: `/usr/local/etc/mosquitto/mosquitto.conf`
4. To have launchd start mosquitto now and restart at login: `brew services start mosquitto`
5. Or, if you don't want/need a background service you can just run: `mosquitto -c /usr/local/etc/mosquitto/mosquitto.conf`

Extending functionalities is straightforward:
1. the java source files in the `src` directory can be modified to add the functionalities one wants.
2. once the src files have been modified, a .jar file can be generated from the .java by running `sh pack_to_jar.sh` from the `jars` directory.
3. the java classes packed in the jar files in the `jars` folder can be then imported in MATLAB using `javaaddpath` as done in `example.m`.
