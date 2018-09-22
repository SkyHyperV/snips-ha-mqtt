**YouTube video link:** <BR>
[![Snips-Home Assistant MQTT Bridge](http://img.youtube.com/vi/x4bo7ru9q2M/0.jpg)](http://www.youtube.com/watch?v=x4bo7ru9q2M)

<BR>

**Architecture Diagram:**<BR>
snips_ha_architecture.pdf<BR><BR>

**Snips Files:**<BR>
mosquitto_for_snips.conf -- make sure to take details from this file and create your own version<BR>
snips.toml -- only edited the mqtt, username, password and bind lines. Compare with yours and update.<BR>

<BR>
  
**HA Files:**<BR>
mosquitto_for_ha.conf -- make sure to take details from this file and create your own version<BR>
configuration.yaml -- you can take the snippet from here and update your own configuration.yaml<BR>

I didn't post the pwfile but you need to create your own with the command below and make sure its in the /etc/mosquitto directory.<BR><BR>
COMMAND: sudo mosquitto_passwd -c /etc/mosquitto/pwfile YOUR_USER e.g. sudo mosquitto_passwd -c /etc/mosquitto/pwfile pi<BR><BR>
Then enter your password (twice) and you should be good to go.<BR><BR>
  
**Testing (from the video):**<BR>
Once you have HA and MQTT Mosquitto working (no error in logs) then you can test subscription to the message bus as I showed in the video by running this on your HA Server:<BR><BR>

**NOTE:** If you don't have 'mosquitto_sub' as a command, then you need to run: apt-get install mosquitto-clients <BR><BR>
sudo mosquitto_sub -t hermes/# -u YOUR_USER -P YOUR_PASSWORD<BR><BR>
Then test audio to Snips and you should see the topics show up on the HA side where you're running the mosquitto_sub command
