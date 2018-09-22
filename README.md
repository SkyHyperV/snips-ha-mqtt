YouTube video link: 

Snips Files:
mosquitto_for_snips.conf -- make sure to take details from this file and create your own version
snips.toml -- only edited the mqtt, username, password and bind lines. Compare with yours and update.

HA Files:
mosquitto_for_ha.conf -- make sure to take details from this file and create your own version
configuration.yaml -- you can take the snippet from here and update your own configuration.yaml

I didn't post the pwfile but you need to create your own with the command below and make sure its in the /etc/mosquitto directory.
COMMAND: sudo mosquitto_passwd -c /etc/mosquitto/pwfile <YOUR USER> e.g. sudo mosquitto_passwd -c /etc/mosquitto/pwfile pi

Then enter your password (twice) and you should be good to go.

Architecture Diagram:
snips_ha_architecture.pdf

Testing (from the video):
Once you have HA and MQTT Mosquitto working (no error in logs) then you can test subscription to the message bus as I showed in the video by running this:
sudo mosquitto_sub -t hermes/# -u <YOUR USER> -P <YOUR PASSWORD>
