ok-functions
============
From https://github.com/rsp/scripts

Source: https://rawgit.com/rsp/scripts/master/ok-functions

To use the functions first source it in Bash or in `~/.bashrc` or `~/.profile`
```
source ok-functions
```

Then you can use:
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
Of course in practice the commands are more like:
```
make && make test && make install; oks
```
but I used ls so you could quickly see how it works.

You can use ok instead of oks for a silent version.

Or you can use e.g.:
```
ls / && ls /bim && ls /usr; ok; sn1
```
to print OK/ERROR but always play the same sound, etc.

I posted those functions in the following answer on Ask Ubuntu:
* [Make a sound once process is complete](https://askubuntu.com/questions/277215/make-a-sound-once-process-is-complete/604116#604116)

They should work on any Linux distro after changing the paths to sounds.

To find good sounds on your system try:
```
for i in /usr/share/sounds/*/stereo/*; do echo $i; paplay $i; sleep 1; done
```
