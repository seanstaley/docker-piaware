**Warning:** This image is built to work on a Raspberry Pi 3 with Docker.

### Requirements
 * Register a Flightaware account ([flightaware.com](http://flightaware.com))
 * Beast data feed (for instance [seanstaley/rpi-dump1090](https://hub.docker.com/r/seanstaley/rpi-dump1090))

### Running
`docker run -d --link <dump1090 container name or ID>:beast --mac-address=<mac address> seanstaley/rpi-piaware <flightaware user> <flightaware password>`

### Configuration
Docker normally assigns a random MAC address every time a container is created. As Flightaware uses your MAC to identify a receiver you have to use the mac-address option to keep it consistent. You can choose any random MAC for this, just keep it the same once you have choosen one.

### Environment variables
Use `BEAST_PORT_30005_TCP_ADDR` and `BEAST_PORT_30005_TCP_PORT` to configure the connection details for the Beast data feed. If you link in a container named `beast` that exposes port 30005 these will be set by Docker directly.

MLAT support is enabled by default. You can set `MLAT` to `no` if you would like to disable it.
