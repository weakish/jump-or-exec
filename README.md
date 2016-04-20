`jump-or-exec` tries to see if an application is already running, and if so, bring the application's window to the front, otherwise launch an instance.
Bind it to a shortcut key and it will be useful!

## Usage

```sh
jump-or-exec command [window_name]
```

## Install

### Dependencies

This script uses [wmctrl](http://tomas.styblo.name/wmctrl/), which is a UNIX/Linux command line tool to interact with an EWMH/NetWM compatible X Window Manager.

### via basher

```sh
; basher install weakish/jump-or-exec
```

Require [basher][] version: `>=39875bc`.

[basher]: https://github.com/basherpm/basher

### manually

You just need to download `jump-or-exec.sh`, and put it into your `$PATH`,
probably after renaming to `jump-or-exec` and `chomd a+x`.


## See also

This script is based on the version in [eshock/.bashrc.d](https://github.com/eshock/.bashrc.d/blob/master/tools/jump-or-exec), in which `window_name` cannot be omitted.

There are also other scripts based on wmctrl, for example, [jumpapp](https://github.com/mkropat/jumpapp) and [brocket](https://github.com/dmikalova/brocket).
Both are more complex^w feature rich.
And I failed to make them work with some applications.
Thus I wrote this script.

Besides wmctrl, it is also possible to implement `jump or exec` in Xlib directly.
For example, here is [a Python script](http://www.aifreedom.com/pluskid/JumpOrExec.html).
The script runs as a daemon, to avoid possible delays when invoking shell script and wmctrl.
The post is written in Chinese, but don't worry, you can read code in Python and code comments in English.
On my machine, `wmctrl` is fast enough.
Thus I consider I don't need a persistent daemon.
