scripts
=======
https://github.com/rsp/scripts

Random shell scripts for different tasks.
Mostly for Linux but I would like them to work on as many
systems as possible - certainly on all POSIX systems.
If anything doesn't work, please post an [issue](#issues).

Work in progress - more to come.

Some of those scripts were written for
[my answers on Stack Exchange](https://stackexchange.com/users/303952/rsp):

* [Make a sound once process is complete](https://askubuntu.com/questions/277215/make-a-sound-once-process-is-complete/604116#604116) (on [Ask Ubuntu](https://askubuntu.com/users/11582/rsp))
* [How can I get my external IP address in bash?](https://unix.stackexchange.com/questions/22615/how-can-i-get-my-external-ip-address-in-bash/194136#194136) (on [Unix & Linux](https://unix.stackexchange.com/users/23774/rsp))
* [How do I find my internal ip address?](https://askubuntu.com/questions/430853/how-do-i-find-my-internal-ip-address/604691#604691) (on [Ask Ubuntu](https://askubuntu.com/users/11582/rsp))
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
### `ga`
Usage: `ga file [file ...]`

Source: https://rawgit.com/rsp/scripts/master/ga

Runs: `git add file [file ...]`

See [ga.md](ga.md) for more info.

### `gcm`
Usage: `gcm your message` (no quoting needed)

Source: https://rawgit.com/rsp/scripts/master/gcm

Runs: `git commit message -m ...`

Running: `gcm your message`
is equivalent to: `git commit -m "your message"`

See [gcm.md](gcm.md) for more info.

### `gpom`
Usage: `gpom`

Source: https://rawgit.com/rsp/scripts/master/gpom

Runs: `git push origin master --tags`

See [gpom.md](gpom.md) for more info.

### `auu`
Usage: `sudo auu`

Source: https://rawgit.com/rsp/scripts/master/auu

Update and upgrade a Debian, Ubuntu or other APT-based Linux system.

See [auu.md](auu.md) for more info.

### `internalip`
Usage: `internalip [TARGET]`

Source: https://rawgit.com/rsp/scripts/master/internalip

Get internal IP address used for outgoing Internet connections.

TARGET is an IP address, `8.8.8.8` by default,
or a host name (if `gethostip` or `getent` are available on the system).

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

Issues
------
For any bug reports or feature requests please
[post an issue on GitHub](https://github.com/rsp/scripts/issues).

Author
------
Rafał Pocztarski - https://github.com/rsp

License
-------
MIT License (Expat). See [LICENSE.md](LICENSE.md) for details.
