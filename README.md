scripts
=======
https://github.com/rsp/scripts

Random shell scripts for different tasks.
Mostly for Linux.

Work in progress - more to come.

Some of those scripts were written for
[my answers on Stack Exchange](https://stackexchange.com/users/303952/rsp):

* [Make a sound once process is complete](https://askubuntu.com/questions/277215/make-a-sound-once-process-is-complete/604116#604116)
* [How can I get my external IP address in bash?](https://unix.stackexchange.com/questions/22615/how-can-i-get-my-external-ip-address-in-bash/194136#194136)

Some are just for my own conveniece. Maybe they would be useful to someone else.

Functions
---------
### `ok-functions`
Usage:
```
sn1
sn2
sn3
ok
oks
```

For example to hear when a long-running command finishes and to hear a different sound on success and on failure:

Example with success:
```
ls / && ls /bin && ls /usr; oks
```
example with error:
```
ls / && ls /bim && ls /usr; oks
```

See [ok-functions.md](ok-functions.md) for more info.

Scripts
-------
### `internalip`
Usage: `internalip [TARGET]`

Source: https://rawgit.com/rsp/scripts/master/internalip

Get internal IP address used for outgoing Internet connections.

TARGET is an IP address, `8.8.8.8` by default.

See [internalip.md](internalip.md) for more info.

### `externalip`
Usage: `externalip [METHOD]`

Source: https://rawgit.com/rsp/scripts/master/externalip

Get external IP address that is visible by servers that you connect to over Internet.

METHOD can be: dns (default), http, https, ftp, telnet.

See [externalip.md](externalip.md) for more info.

### `externalip-benchmark`
Usage: `externalip-benchmark`

Source: https://rawgit.com/rsp/scripts/master/externalip-benchmark

Find what services providing external IP address via http and https are the fastest.

See [externalip-benchmark.md](externalip-benchmark.md) for more info.

Installation
------------
Most of those scripts should be stand-alone and can be copied in any place.

My recommendation is to make a `~/bin` or `~/scripts` directory:
```
mkdir ~/bin
```
and put this in your `~/.bashrc` or `~/.profile`:
```
[ -d "$HOME/bin" ] && PATH="$HOME/bin:$PATH"
```
That way it's easy to put any script there:
```
cd ~/bin
wget https://rawgit.com/rsp/scripts/master/example
less example # see what was downloaded
chmod a+x example
```
And use it at will.
Of course always see what was downloaded first.

Author
------
Rafał Pocztarski - https://github.com/rsp

License
-------
MIT License (Expat). See [LICENSE.md](LICENSE.md) for details.
