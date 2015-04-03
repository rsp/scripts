internalip
==========
From https://github.com/rsp/scripts

Usage: `internalip [TARGET]`

Source: https://rawgit.com/rsp/scripts/master/internalip

Get internal IP address used for outgoing Internet connections.
This is an IP address of your computer's network interface
that would be used to connect to a given target.

The TARGET is optional and by default it is `8.8.8.8`
(which is the [Google's public DNS resolver](https://developers.google.com/speed/public-dns/docs/using)).
It can be an IP address or a host name (if `gethostip` or `getent` are available on the system).

Note: this is not necessarily the same IP as the public IP that you visible under while connecting to the Internet
(for that use [externalip](externalip.md)).

Unlike most of the solutions to get your IP from the output of programs like `ifconfig` or `hostname` that are usually recommended, often with a need to manually choose a network interface, this method has an advantage that the result is based on your routing tables and you get the IP address that is actually used to connect to a given target (the public Internet by default).

The idea was taken from
[this Stack Overflow answer](https://stackoverflow.com/questions/13322485/how-to-i-get-the-primary-ip-address-of-the-local-machine-on-linux-and-os-x#25851186)
by [Collin Anderson](https://stackoverflow.com/users/131881/collin-anderson).
