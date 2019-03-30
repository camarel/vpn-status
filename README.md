# VPN-Status

## Description

VPN-Status is a simple web page that displays the status of the VPN connection. It is intended to work on an OpenWRT router which acts as a VPN client. Its outside of Luci, as a standalone 'application', so no login to the router is required. This has the advantage that you can quickly check the status, independent of the device you currently use.

Vpnstatus only checks the connection status with the proper tools provided by the router itself, thus it does not connect to an external website like ipleak or similar.

To check the connection status it does the following:

* Ping the VPN server. Or if you like the router behind the VPN server.
* Traceroute the first 5 hops to a generic website like wikipedia. This indicates, if the traffic goes through the expected hosts. You can define a regex pattern to match the hostname or ip address that you expect to find in the traceroute.



## Installation

The files from the www directory go directly into the /www folder on the OpenWRT router.

Make the CGI script executable:

```
chmod +x /www/cgi-bin/vpnstatus
```

In the file `/www/vpnstatus.html`: To match your needs, you must edit the following JavaScript variables around line 70:

* pingHosts: a list of hosts you want to ping. One is surely the VPN server you are connecting to.
* traceMatch: a pattern to match, can be a hostname or an ip address that should be contained in the traceroute.



## Usage

To access the status page, simply go to your routers IP address, followed by /vpnstatus.html.

Example:
http://192.168.1.1/vpnstatus.html


## Author

**Claudio Marelli**

* [github/camarel](https://github.com/camarel)

## License

Copyright © 2019 Claudio Marelli
Released under the MIT license.


