scripts
=======
https://github.com/rsp/scripts

Random shell scripts for different tasks.
Mostly for Linux.

Some of those scripts were written as examples for
[my answers on Stack Exchange](https://stackexchange.com/users/303952/rsp).

Some are just for my own conveniece. Maybe they would be useful to someone else.

Scripts
-------
### `internalip`
Usage: `internalip [TARGET]`

Get internal IP address used for outgoing Internet connections.

See [internalip.md](internalip.md) for more info.

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
