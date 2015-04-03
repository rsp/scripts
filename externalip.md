externalip
==========
From https://github.com/rsp/scripts

Usage: `externalip [METHOD]`

Source: https://rawgit.com/rsp/scripts/master/externalip

Get external IP address that is visible by servers that you connect to over Internet.

Note: this is not necessarily the same IP as the one that is used by your computer's network interface
(for that use [internalip](internalip.md)).

METHOD can be: dns (default), http, https, ftp, telnet.

The http and https methods are using the `whatismyip.akamai.com` service that showed the best performance in all my tests (from Warsaw, Poland).

Use the [externalip-benchmark](externalip-benchmark.md) script to find the best server for your location.

