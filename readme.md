# OpenVPN restrict

This is a script to be used in OpenVPN server to restrict connecting
clients to connect only to the specified hosts. List of allowed to
connect hosts configured per client, can include hostnames, IP addresses
or CIDR blocks.

It uses `learn-address` feature of the OpenVPN and IP Tables to allow
connection to only specified IPs or hosts.

## Usage


1. Place script in OpenVPN directory (in the example below
`/etc/openvpn/connect` ) and add following two lines to the server
configuration file:

```
learn-address /etc/openvpn/connect
client-disconnect /etc/openvpn/connect
```

2. Edit file `/etc/openvpn/allow_ips` and add lines in the format:


```
cn-name: 192.168.0.0/24 10.8.0.0/16 web01 db02 app01
```

Here `cn-name` is name of certificate built by Easy-RSA scripts.
