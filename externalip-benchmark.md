externalip-benchmark
====================
From https://github.com/rsp/scripts

Usage: `externalip-benchmark`

Source: https://rawgit.com/rsp/scripts/master/externalip-benchmark

Find what services providing external IP address via http and https are the fastest.

The results were used to tune the [externalip](externalip.md) script
and to recommend good methods in this answer on Stack Exchange:

* [How can I get my external IP address in bash?](https://unix.stackexchange.com/questions/22615/how-can-i-get-my-external-ip-address-in-bash/194136#194136)

## Results of experiments

### The fastest method using DNS:
```
dig +short myip.opendns.com @resolver1.opendns.com
```

### The fastest using HTTP:
```
curl -s http://whatismyip.akamai.com/
```
Not always **the** fastest, but consistently very fast.

### The fastest using HTTPS:
```
curl -s https://4.ifcfg.me/
```
Some were faster but with invalid certificates.

### Using telnet via nc:
```
nc 4.ifcfg.me 23 | grep IPv4 | cut -d' ' -f4
```

### Using telnet via telnet:
```
telnet 4.ifcfg.me 2>&1 | grep IPv4 | cut -d' ' -f4
```

Those commands are run by [externalip](externalip.md) invoked with the following arguments:

	externalip dns
	externalip http
	externalip https
	externalip telnet
	externalip ftp

Currently `externalip telnet` uses `nc` for the connection.

There are a lot of options of different servers providing the external IP especially via HTTP.
I made those benchmarks to see if any of them are better than the others and I was surprised by the results.
E.g. one of the most widely recommended ifconfig.me was almost always the slowest for me, sometimes taking many seconds to respond. Many don't work over HTTPS. Some have invalid certificates.

This is the source of the externalip-benchmark script:

* https://raw.githubusercontent.com/rsp/scripts/master/externalip-benchmark

You can run it yourself to see which services mentioned here are worth using:

    wget https://raw.githubusercontent.com/rsp/scripts/master/externalip-benchmark
    chmod a+x externalip-benchmark
    ./externalip-benchmark

My results that I got on 2015-04-03 from Warsaw
- the addresses have been changed to protect the innocent:
```
0.099s http://whatismyip.akamai.com/ - answer='172.31.13.37'
0.107s http://ident.me/ - answer='172.31.13.37'
0.108s http://tnx.nl/ip - answer='172.31.13.37'
0.109s http://ip.tyk.nu/ - answer='172.31.13.37'
0.114s http://ipof.in/txt - answer='172.31.13.37'
0.115s http://ifcfg.me/ - answer='172.31.13.37'
0.117s http://ipecho.net/plain - answer='172.31.13.37'
0.295s http://ip.appspot.com/ - answer='172.31.13.37'
0.305s http://wgetip.com/ - answer='172.31.13.37'
0.346s http://icanhazip.com/ - answer='172.31.13.37'
0.352s http://l2.io/ip - answer='172.31.13.37'
0.434s http://bot.whatismyipaddress.com/ - answer='172.31.13.37'
0.509s http://curlmyip.com/ - answer='172.31.13.37'
0.509s http://curlmyip.com/ - answer='172.31.13.37'
0.659s http://corz.org/ip - answer='172.31.13.37'
0.663s http://eth0.me/ - answer='172.31.13.37'
6.114s http://ifconfig.me/ - answer='172.31.13.37'
```
Best https response times:
```
0.029s https://curlmyip.com/ - answer=''
0.029s https://curlmyip.com/ - answer=''
0.029s https://l2.io/ip - answer=''
0.029s https://tnx.nl/ip - answer=''
0.080s https://whatismyip.akamai.com/ - answer='172.31.13.37'
0.112s https://ipecho.net/plain - answer=''
0.187s https://ip.tyk.nu/ - answer='172.31.13.37'
0.204s https://ipof.in/txt - answer='172.31.13.37'
0.213s https://ident.me/ - answer='172.31.13.37'
0.250s https://ifcfg.me/ - answer='172.31.13.37'
0.440s https://ip.appspot.com/ - answer='172.31.13.37'
0.574s https://corz.org/ip - answer='Minimum check interval is 1 minute!NOTE: 10 infractions = banned!'
0.659s https://icanhazip.com/ - answer='172.31.13.37'
0.880s https://eth0.me/ - answer='172.31.13.37'
1.322s https://bot.whatismyipaddress.com/ - answer='You appear to be an automated script. For API details please visit http://whatismyipaddress.com/api'
5.643s https://ifconfig.me/ - answer=''
10.001s https://wgetip.com/ - answer=''
```
Best average ping times:
```
11.078 //whatismyip.akamai.com/
36.828 //tnx.nl/ip
39.288 //ipof.in/txt
39.796 //ip.tyk.nu/
40.586 //ipecho.net/plain
40.883 //ident.me/
43.659 //ifcfg.me/
46.781 //l2.io/ip
66.198 //ip.appspot.com/
124.038 //corz.org/ip
133.978 //wgetip.com/
157.306 //icanhazip.com/
161.243 //curlmyip.com/
162.871 //curlmyip.com/
999999 //bot.whatismyipaddress.com/
999999 //eth0.me/
999999 //ifconfig.me/
```
Any important service missing? Please [post an issue](https://github.com/rsp/scripts/issues).
