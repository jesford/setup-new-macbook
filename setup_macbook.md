# Notes on setting up my MacBook


### 3rd Party Apps I like to have

- Download from websites, install, & drag icon to dock:
   - Google Chrome
   - VLC media player
   - MacTex (package includes TexShop)
   - Atom
     - enable packages: linter, linter-flake8 (& check box "Flake Errors")
     - disable packages: tree-view (don't like the side bar)
     - choose pretty color theme
   - ~~Aquamacs~~
	   - ~~Turn off scratch buffer: Aquamacs > Preferences > search for
         "scratch" to find setting for "Show Scratch Buffer On
         Startup", and Toggle off & save settings~~
	   - ~~Turn on line numbering: Options > View > Line Numbering~~


### Organization & Visual Preferences

- clean up dock applications to personal preferences
- System Preferences:
	- set hot corners with Mission Control
	- change Desktop background & screen saver
	- adjust energy saver settings


### Terminal & Command Line

- Terminal > Preferences > Text
  - Font: Courier 14 pt.
  - Text: Text = pale yellow, Bold Text = pale orange, Selection = lavendar, *select:* Antialias text, Use bold
    fonts, Allow blinking text, Display ANSI colors
  - Cursor: Cursor = lavendar, *select:*  Block, Blink Cursor

- Terminal > Preferences > Window
  - Background: Color & Effects = dark cyan

- copy old ```.bash_profile``` to home directory OR create new one and
include my basic preferences:
```sh
alias rm='rm -i' 
alias ls='ls -phF'
export PS1="\u@macbook:\w $ "  #make nicer prompt
alias amacs='open -a Aquamacs'
alias chrome='open -a Google\ Chrome'
cl() { cd "$@" && ls && pwd; }
export CLICOLOR=1
export LSCOLORS=gxBxhxDxfxhxhxhxhxcxcx
#export LSCOLORS=ExFxCxDxBxegedabagacad #for lighter background
#export LSCOLORS="ExGxBxDxCxEgEdxbxgxcxd" #to emulate standard Linux
```

### Python
- Download and install [Anaconda](https://www.continuum.io/downloads) for OS X, 
choosing the Python 3 version, and using all default settings.
- Create Python 2.7 and 3.4 environments containing all the standard Anaconda packages:
```sh
conda create -n py27 python=2.7 anaconda
conda create -n py34 python=3.4 anaconda
```
- Each environment can then be activated with, e.g., ```source activate py27``` and deactivated with ```source deactivate```.


### Version Control
- From App Store, Install XCode (have to open it & agree to license)
- Install Git (after installing Xcode) and configure Git settings, following these instructions:
https://help.github.com/articles/set-up-git/
- Save GitHub password in Git, following these instructions:
https://help.github.com/articles/caching-your-github-password-in-git/
- Make Atom the default Git editor: ```git config --global core.editor "atom --wait"```
- Enable tab-completion for Git commands:
  - Run this: ```curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o ~/.git-completion.bash```
  - Add this line to .bash\_profile: ```test -f ~/.git-completion.bash && . $_```

### Homebrew
- After installing XCode (for version control, above), follow these
  instructions (outlined below): http://coolestguidesontheplanet.com/installing-homebrew-os-x-yosemite-10-10-package-manager-unix-apps/
- Get the XCode Command Line Tools ($\sim$1 hour download, then have
to open and agree to license):
```sh
xcode-select --install
```
- Run script on commad line:
```sh
ruby -e "$(curl -fsSL
https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
- Download and install Xquartz: http://xquartz.macosforge.org/landing/
- Check for issues with ```brew doctor```
- Install packages with Homebrew:
	- ```brew install wget```
	- ```brew install somethingelse```

### Miscellaneous
- Copy over Music & Photos
- Copy non-defunct subdirectories & files beneath home directory
