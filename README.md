# Dockerized Media Server

My first attempt at a useful project using containers.

## Constraints and Requirements
* Be as "Docker-ey" as possible.
* Must run on a single host, with a single NIC on Ubuntu (Trusty or Xenial)
* Containers must route ALL traffic through a VPN gateway.
* Host machine will not connect to the VPN.
* Web gui's for services in containers must be accessible from hosts on the lan.
* Container cli's must be accessible from host.

## Design
* File, plex, dyndns and openSSH services on host.
* Host provides CIFS mounts for windows htpc's on local network.
* Sabnzbd and transmission-daemon services in containers.


## TODO List
* Evaluate possble approaches to the vpn gateway.
* Initial approach is to give gateway container two virtual interfaces.
* "External" ifc is a bridge from the hosts physical interface. "Internal" will
get a private IP in a separate subnet for containers.
* All containers will use the Internal ifc of the VPN gatway container as
their default route.
* Gateway container's default route is the bridge to host
physical interface, and performs routing between the lan and container subnets.
* Network routing tests.
* Containerize services.
* Access to web gui's of containerized services (Port forwarding from host
directly in to containers?)


## Installation

TODO: Build something worth installing. Describe the installation process.

## Usage

TODO: Build something worth using. Describe it's usage.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

TODO: Write history

## Credits

TODO: Write credits

## License

TODO: Write license
