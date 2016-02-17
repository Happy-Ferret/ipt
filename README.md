# iPipeTo [![NPM version](https://badge.fury.io/js/ipt.svg)](https://npmjs.org/package/ipt) [![Build Status](https://travis-ci.org/ruyadorno/ipt.svg?branch=master)](https://travis-ci.org/ruyadorno/ipt)

> Interactive Pipe To


## About

**ipt** (pronounced iPipeTo) introduces the missing cli interactive workflow. It takes any kind of list as an input and uses that list to build an interactive interface to let you select an element from it.

Stop manually dragging your mouse around to copy output data from a terminal, using the **ipt** workflow you can pipe data from a command and select what to copy to clipboard from a convenient visual menu.

Selected data is also output to _stdout_ allowing for easily composing various workflows, just create your custom alias.


## Usage

The default behavior of **ipt** is to allow for the selection of one item from the interactive list, once selected this item will be copied to your clipboard and output to _stdout_.

In the example below we show a menu containing the local directories.

```sh
ls | ipt
```

> **iPipeTo** is the DIY kit for interactive interfaces in the command-line, plug whatever you want in, do something fun with the output!


## [Awesome workflow Gallery](gallery.sh)

```sh
# irm: Selects files to delete from current folder (recommended to use trash instead of rm -rf)
alias irm="ls | ipt -m -n | xargs rm -rf"

# irebase: Interactive build a list of git commits from log and rebase from selected one
alias irebase="git --no-pager log --oneline | ipt -n | cut -d ' ' -f 1 | xargs -o git rebase -i"
```

Got an awesome alias idea? [Send us a PR to add it to our gallery](gallery.sh)


### Beguinners Help

> Do you love all these fancy interactions from the examples above but don't quite follow all this unix jargon? Worry not, in the Awesome Gallery just above we have some common workflow scripts pre configured to be used as simple shell commands.

> We also provide a simple example of how to get the commands in the Install section below.


## Install

Install it easily using **npm**:

```sh
$ npm install -g ipt
```

_Keep in mind that you'll need to have at least **Node.js** > 0.12 installed_

### Beguinners Setup

So do you like the previous examples but are not super confident on how to configure these commands? Although I'd really recommend you to take a look at [how to do it yourself](http://askubuntu.com/questions/17536/how-do-i-create-a-permanent-bash-alias), below is a quick script for you to run in your terminal and have all of our [gallery](gallery.sh) scripts at once.

#### OSX

```sh
curl -fsSL https://raw.githubusercontent.com/ruyadorno/ipt/master/gallery.sh >> ~/.bash_profile
```

#### Unix

```sh
curl -fsSL https://raw.githubusercontent.com/ruyadorno/ipt/master/gallery.sh >> ~/.bashrc
```


## Help

```sh
Usage:
  ipt [<path>]

Specify a file <path> or pipe some data from stdin to start interacting.

Options:
  -v --version       Displays app version number
  -h --help          Shows this help message
  -d --debug         Prints original node error messages to stderr on errors
  -e --file-encoding Sets a encoding to open <path> file, defaults to utf8
  -m --multiple      Allows the selection of multiple items
  -s --separator     Defines a separator to be used to split input into items
  -n --no-copy       Do not copy selected item(s) to clipboard
```


## Supported OS Terminals

**iPipeTo** should run just fine in any of the [Inquirer.js](https://github.com/SBoudrias/Inquirer.js) supported terminals:

- **Mac OS**:
  - Terminal.app
  - iTerm
- **Linux (Ubuntu, openSUSE, Arch Linux, etc)**:
  - gnome-terminal (Terminal GNOME)
  - konsole
- **Windows**\*:
  - cmd.exe
  - Powershell
  - Cygwin

_\* Feedback wanted to confirm which features are available on a Windows cli_

### Contributing

**Bug fixes / code changes**: Please provide tests covering your changes, update docs accordingly and keep your changes to a single commit.


## Credits

**iPipeTo** wouldn't be possible if not for the amazing [Inquirer.js](https://github.com/SBoudrias/Inquirer.js) that provides all these sweet interactive interfaces.

### Created by

[![Ruy Adorno](https://avatars.githubusercontent.com/u/220900?v=3&s=460)](http://ruyadorno.com) |
---|
[Ruy Adorno](http://ruyadorno.com) |

## License

MIT © [Ruy Adorno](http://ruyadorno.com)
