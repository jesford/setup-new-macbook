# Notes on setting up my MacBook


### 3rd Party Apps I like to have

- Download from websites, install, & drag icon to dock:
   - Google Chrome
   - VLC media player
   - MacTex (package includes TexShop)
   - Atom
     - enable packages: python-indent, linter, linter-flake8 (& check box "Flake Errors")
     - disable packages: tree-view (don't like the side bar)
     - choose pretty color theme
       - currently I like UI theme "Atom Dark" and Syntax Theme "Base16 Tomorrow Dark"


### Organization & Visual Preferences

- clean up dock applications to personal preferences
- System Preferences:
	- set hot corners with Mission Control
	- change Desktop background & screen saver
	- adjust energy saver settings


### Terminal & Command Line

- Terminal > Preferences > Text
  - Set "Pro" theme as the default
  - Font: Courier 14 pt.
  - Text: *select:* Use bold fonts, Allow blinking text, Display ANSI colors
  - Cursor: *select:* Block, Blink Cursor

- copy old ```.bash_profile``` to home directory OR create new one and
include my basic preferences:
```sh
alias rm='rm -i'
alias ls='ls -phF'
export PS1="\u@macbook:\w $ "  #make nicer prompt
alias atom='open -a atom'
alias chrome='open -a Google\ Chrome'
alias jup='jupyter notebook'
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
- Install [Jupyter Notebook extensions](http://jupyter-contrib-nbextensions.readthedocs.io/en/latest/index.html), and enable the configurator:
```
conda install -c conda-forge jupyter_contrib_nbextensions
conda install -c conda-forge jupyter_nbextensions_configurator
```

### Version Control
- From App Store, Install XCode (have to open it & agree to license)
- Save GitHub password in Git, following these instructions:
https://help.github.com/articles/caching-your-github-password-in-git/
- Make Atom the default Git editor: ```git config --global core.editor "atom --wait"```
- Enable tab-completion for Git commands:
  - Run this: ```curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o ~/.git-completion.bash```
  - Add this line to .bash\_profile: ```test -f ~/.git-completion.bash && . $_```

### Homebrew
- After installing XCode (for version control, above), follow these
  instructions (outlined below):
- Get the XCode Command Line Tools (download, then have
to open and agree to license):
```sh
xcode-select --install
```
- Follow these instructions to install: https://brew.sh/
- Check for issues with ```brew doctor```
- Install packages with Homebrew:
```sh
brew install wget
brew install tree
brew install graphviz
```

### Miscellaneous
- Copy over Music & Photos
- Copy non-defunct subdirectories & files beneath home directory
