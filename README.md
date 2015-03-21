# Bash files

This is my bash files Project for Linux. It also works on Mac OS X with a few minor limitations. The project grew out of the tweaks and additions I applied for my personal use.

Some inspiration was taken from projects such as [oh-my-zsh
](https://github.com/robbyrussell/oh-my-zsh/tree/master/lib), [bash-it](https://github.com/revans/bash-it) and others.

`Bash files` is a work in progress project, everything is still a bit quick and dirty and constantly moving. I hope you enjoy it nevertheless.

Feel free to contribute, reuse, clone, etc.

-binaryanomaly

<br>
---

#### Screenshot
The current version (15.03.2015) looks like this:

![Bash_files start screen](http://i.imgur.com/2D5fg2D.png "Bash_files start screen")

<br>
---
<br>

### Updates

##### 15.03.2015
- Added distribution info

##### 14.03.2015
 - Added public ip info

<br>
---
<br>

### Feature list

##### Generic features
 - Config vars for features
 - OS type detection support for Linux and OS X
 - Cross-platform robust checks


##### Start screen - Info sections
 - Hostname (figlets, lolcat supported)
 - CPU, RAM info
 - Distribution info
 - External (public) IP
 - System info (kernel, architecture)
 - File system info
 - Last logins
 - Random bash comand info (whatis)
 - Reboot required check and message on welcome screen and/or in prompt

Most sections can be turned on and off in `config/config.sh`

#### Functions
 - **extip** - Display external (public) ip using dig/opendns

<br>
---
<br>


### Initial installation procedure

Clone the repository into your home directory, it will create the `.bash_files` subdirectory:

```bash
git clone https://github.com/binaryanomaly/bash_files ~/.bash_files
```


#### Invoke init file from .bashrc (.bash_profile on Mac OS X)

Add the following at the end of your `.bashrc` or `.bash_profile` in your home directory:

```bash
# Bash_dotfiles initialization
if [ -f ~/.bash_files/init.sh ]; then
    . ~/.bash_files/init.sh
fi
```

<br>

#### Dependencies

The following Standard Linux commands are needed:

- `dig` to determine the public ip via opendns
- `free` for ram info
- `df` for diskspace info
- `last` for last logins
- `whatis` for command related infos


#### Optional dependencies

The following optional packages are recommended to be installed:

- `figlet` for big ascii letter hostname
- `lolcat` to colorize the ascii letter hostname

Install them using apt (Linux) or homebrew (Mac)

The script will autodetect if each of those is installed and disable the features if not found.



<br>
---
<br>

### Directory and file structure

The project lives in `~/.bash_files/` 

| Directory | Description |
| ---- | ----------- |
| aliases/  | Directory for alias definitions - `*aliases.sh` gets sourced |
| config/  | Directory for config files - `*config.sh` gets sourced |
| lib/ | Directory where base functionality is stored - `base*.sh` gets sourced |

<br>


| File | Description |
| ---- | ----------- |
| init.sh  | Init file that sources all the other dirs/files |

<br>
---
<br>

### Conventions

 - Use `_bf_` prefix for variable names