scripts [![License][license-img]][license-url] [![GitHub Stars][stars-img]][stars-url] [![GitHub Forks][forks-img]][forks-url] [![GitHub Watchers][watchers-img]][watchers-url] [![Tweet][tweet-img]][tweet-url]
=======
[github-url]: https://github.com/rsp/scripts
[readme-url]: https://github.com/rsp/scripts#readme
[issues-url]: https://github.com/rsp/scripts/issues
[stars-url]: https://github.com/rsp/scripts/stargazers
[watchers-url]: https://github.com/rsp/scripts/watchers
[forks-url]: https://github.com/rsp/scripts/network/members
[stars-img]: https://img.shields.io/github/stars/rsp/scripts.svg?style=social&amp;label=Stars
[forks-img]: https://img.shields.io/github/forks/rsp/scripts.svg?style=social&amp;label=Forks
[watchers-img]: https://img.shields.io/github/watchers/rsp/scripts.svg?style=social&amp;label=Watchers
[tweet-img]: https://img.shields.io/twitter/url/https/github.com/rsp/scripts.svg?style=social
[tweet-url]: https://twitter.com/intent/tweet?text=Shell+scripts+by+@pocztarski:&url=https%3A%2F%2Fgithub.com%2Frsp%2Fscripts
[license-url]: https://github.com/rsp/scripts/blob/master/LICENSE.md
[license-img]: https://img.shields.io/github/license/rsp/scripts.svg
[travis-url]: https://travis-ci.org/rsp/scripts
[travis-img]: https://travis-ci.org/rsp/scripts.svg?branch=master
[snyk-url]: https://snyk.io/test/github/rsp/scripts
[snyk-img]: https://snyk.io/test/github/rsp/scripts/badge.svg
[github-follow-url]: https://github.com/rsp
[github-follow-img]: https://img.shields.io/github/followers/rsp.svg?style=social&label=Follow
[twitter-follow-url]: https://twitter.com/intent/follow?screen_name=pocztarski
[twitter-follow-img]: https://img.shields.io/twitter/follow/pocztarski.svg?style=social&label=Follow
[stackoverflow-url]: https://stackoverflow.com/users/613198/rsp
[stackexchange-url]: https://stackexchange.com/users/303952/rsp
[stackexchange-img]: https://stackexchange.com/users/flair/303952.png

by [Rafał Pocztarski](https://pocztarski.com/)
[![Follow on GitHub][github-follow-img]][github-follow-url]
[![Follow on Twitter][twitter-follow-img]][twitter-follow-url]

https://github.com/rsp/scripts

Random shell scripts for different tasks,
written mostly for answers on Stack Overflow:
<br/>
[![Follow on Stack Exchange][stackexchange-img]][stackoverflow-url]

Examples
--------
Some common command shortcuts for Git et al.:

* [`auu`](#auu) - apt-get update and upgrade for Debian or Ubuntu
* [`ga`](#ga) - git add
* [`gcm`](#gcm) - git commit with message quoted automatically
* [`gpod`](#gpod) - git push origin develop (with/without tags)
* [`gpom`](#gpom) - git push origin master (with/without tags)

Some other tools and commands:

* [`internalip`](#internalip) - get your internal IP address
* [`externalip`](#externalip) - get your external IP address
* [`sound`](#ok-functions) - play a sound a wait to finish
* [`soundbg`](#ok-functions) - play a sound in background
* [`sn1`](#ok-functions)/[`sn2`](#ok-functions)/[`sn3`](#ok-functions) - good sounds for notifications
* [`ok`](#ok-functions) - prints OK/ERROR if the last command succeeded/failed
* [`oks`](#ok-functions) - like `ok` but with different sounds played on success/failure

Details
-------
Those commands are
mostly for Linux but I would like them to work on as many
systems as possible - certainly on all POSIX systems.
If anything doesn't work, please post an [issue](#issues).

Work in progress - more to come. See:

* [Installation](#installation)
* [Issues](#issues)
* [Author](#author)
* [License](#license)

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
(note the automatic quoting)

See [gcm.md](gcm.md) for more info.

### `gpodn`
Usage: `gpodn`

Source: https://rawgit.com/rsp/scripts/master/gpodn

Runs: `git push origin develop` (no tags)

See [gpodn.md](gpodn.md) for more info.

### `gpodt`
Usage: `gpodt`

Source: https://rawgit.com/rsp/scripts/master/gpodt

Runs: `git push origin develop --tags`

See [gpodt.md](gpodt.md) for more info.

### `gpod`
Usage: `gpod`

Source: https://rawgit.com/rsp/scripts/master/gpod

Runs: `git push origin develop --tags`
(by default it's the same as `gpodt`)

See [gpod.md](gpod.md) for more info.

### `gpomn`
Usage: `gpomn`

Source: https://rawgit.com/rsp/scripts/master/gpomn

Runs: `git push origin master` (no tags)

See [gpomn.md](gpomn.md) for more info.

### `gpomt`
Usage: `gpomt`

Source: https://rawgit.com/rsp/scripts/master/gpomt

Runs: `git push origin master --tags`

See [gpomt.md](gpomt.md) for more info.

### `gpom`
Usage: `gpom`

Source: https://rawgit.com/rsp/scripts/master/gpom

Runs: `git push origin master --tags`
(by default it's the same as `gpomt`)

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
Those commands describes as functions need to be installed differently,
see below.

### Installing scripts
My recommendation is to make a `~/bin` or `~/scripts` directory:
```sh
mkdir ~/bin
```
and put this in your `~/.bashrc` or `~/.profile`:
```
[ -d "$HOME/bin" ] && PATH="$HOME/bin:$PATH"
```
That way it's easy to put any script there:
```sh
cd ~/bin
wget https://rawgit.com/rsp/scripts/master/example
less example # see what was downloaded
chmod a+x example
```
And use it at will.
Of course always see what was downloaded first.

### Installing functions
Those commands described as functions need to be sourced to work,
either manually or in a file like `.profile`, `.bashrc` etc.

They don't have to be in your PATH and they don't have to be executable.
You can download them whenever you want, for example in your $HOME directory:
```sh
cd ~
wget https://rawgit.com/rsp/scripts/master/example-functions
less example-functions # see what was downloaded
```
Now you source them with `.` (dot) or `source` command:
```sh
. example-functions
```
If you put the sourcing line in your `.profile` or `.bashrc` they will be
available after all logins.

Issues
------
For any bug reports or feature requests please
[post an issue on GitHub][issues-url].

Author
------
[**Rafał Pocztarski**](https://pocztarski.com/)
<br/>
[![Follow on GitHub][github-follow-img]][github-follow-url]
[![Follow on Twitter][twitter-follow-img]][twitter-follow-url]
<br/>
[![Follow on Stack Exchange][stackexchange-img]][stackoverflow-url]

License
-------
MIT License (Expat). See [LICENSE.md](LICENSE.md) for details.
