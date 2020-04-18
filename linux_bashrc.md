'''bash
# .bashrc
[[ $- != *i* ]] && return
# Source global definitions
if [ -f /etc/bashrc ]; then
. /etc/bashrc
fi

#Setup the environment for the PSI pmodules
#idocumentation : https://amas.psi.ch/Pmodules
if [ -f /etc/scripts/pmodules.sh ]; then
        . /etc/scripts/pmodules.sh
fi

#To load specific MX enviroment for each shell, uncomment one of the two following lines:
#. /etc/scripts/mx_sls.sh
#. /etc/scripts/mx_fel.sh

# Uncomment the following line if you don't like systemctl's auto-paging feature:
# export SYSTEMD_PAGER=

alias salloc="salloc -N 1 -p shared -t 7-00:00:00"
alias salgpu="salloc --account=gpu -p gpu -t 7-00:00:00"

alias tombin="cd /afs/psi.ch/project/TOMCAT_pipeline/RA/tomcat_pipeline/bin/"

alias imagej="/das/work/p12/p12926/softwares/Fiji.app_40GB_20161214_1.51j/ImageJ-linux64 --system &"
alias 3dslicer="cd /das/work/p12/p12926/softwares/Slicer-4.8.1-linux-amd64/ && ./Slicer &"

alias pyt17c="cd /das/work/p12/p12926/codes_Hong/pyScript_t17c/"
alias dat17c="cd /das/work/p12/p12926/tomcat_20170501_t17c/disk1/disk1/"

alias pyt17e="cd /das/work/p12/p12926/codes_Hong/pyScript_t17e/"
alias dat17e="cd /das/work/p12/p12926/tomcat_20170918_t17e/disk9/"

alias pyt18b="cd /das/work/p12/p12926/codes_Hong/pyScript_t18b/"
alias dat18b="cd /das/work/p12/p12926/tomcat_20180613_t18b/"

alias pyt18c="cd /das/work/p12/p12926/codes_Hong/pyScript_t18c/"
alias dat18c="cd /das/work/p16/p16830/tomcat_20180912_t18c/disk4/"

alias pyt18d="cd /das/work/p12/p12926/codes_Hong/pyScript_t18d/"
alias dat18d="cd /das/work/p12/p12926/tomcat_20181128_t18d"

alias pyt18e="cd /das/work/p12/p12926/codes_Hong/pyScript_t18e/"
alias dat18e="cd /das/work/p16/p16830/tomcat_20181205_t18e/"

alias cristina="cd /das/work/p12/p12153/"
alias adrian="cd /das/work/p17/p17374/"
alias christoph="cd /das/work/p18/p18009/"

alias vsc="sh /das/work/p12/p12926/softwares/VSCode-linux-x64/bin/code"

alias startPy="module load psi-python27/2.3.0 && source activate /das/work/p12/p12926/PythonEnv/python27/ && cd /das/work/p12/p12926/codes_Hong/ && ls && pwd && cd /das/work/p12/p12926/codes_Hong/"
alias startgpu="module load psi-python36/4.4.0 && source activate /das/work/p12/p12926/PythonEnv/tfgpu36/ && cd /das/work/p12/p12926/codes_Hong/pyScript_gpu && ls && pwd && cd /das/work/p12/p12926/codes_Hong/pyScript_gpu"

alias startEnv="module load psi-python27/2.3.0 && export CONDARC=/afs/psi.ch/project/TOMCAT_pipeline/Anaconda/.condarc_py27ana230 && source activate env-xu && cd /das/work/p12/p12926/ && ls && pwd"

alias start="module load psi-python27/2.3.0 && source activate /das/work/p12/p12926/PythonEnv/xu27/ && cd /das/work/p12/p12926/codes_Hong/ && ls && pwd && gnome-terminal --window -e top --role=ROLE --title='xu_h1@ra-l-002 | WATCH TOP' --zoom=0.9 && gnome-terminal --window -e 'watch squeue' --role=ROLE --title='xu_h1@ra-l-002 | WATCH SQUEUE' --zoom=0.9 && gnome-terminal --window -e pwd --role=ROLE --title='xu_h1@ra-l-002 | WATCH DOCUMENTS' --zoom=0.9 && gnome-terminal --window -e '/das/work/p12/p12926/softwares/Fiji.app_40GB_20161214_1.51j/ImageJ-linux64' --role=ROLE --title='xu_h1@ra-l-002 | ImageJ' --zoom=0.9 && pwd "

alias paraview="module load paraview/5.4.1 && paraview --mesa"

export SITK_SHOW_COMMAND="/das/work/p12/p12926/softwares/Fiji.app_40GB_20161214_1.51j/ImageJ-linux64 --system &"
export SITK_SHOW_EXTENSION=".tif"

export SBATCH_PARTITION=day

current_date_time="`date +%Y.%m.%d-%H:%M:%S`";
echo "* PSI * Xu, Hong * $SBATCH_PARTITION *  $current_date_time"

export HISTSIZE=10000
export HISTFILESIZE=120000

export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/das/work/p12/p12926/softwares/Slicer-4.8.1-linux-amd64/lib/Slicer-4.8/cli-modules/
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/das/work/p12/p12926/softwares/Slicer-4.8.1-linux-amd64/lib/Slicer-4.8/
export PATH="$PATH:/das/work/p12/p12926/PythonEnv/xu27"

export VIRTUAL_ENV_DISABLE_PROMPT=1
#export PS1="[\d-\t] \u@\h: \w\n\W > \[$(tput sgr0)\]"

alias vim="/das/work/p12/p12926/vim/bin/vim"
alias qfind="find . -name "                 # qfind:    Quickly search for file
alias lr='ls -R | grep ":$" | sed -e '\''s/:$//'\'' -e '\''s/[^-][^\/]*\//--/g'\'' -e '\''s/^/   /'\'' -e '\''s/-/|/'\'' | less'
alias lss='ls -ahl && pwd'
alias cd..='cd ../'                         # Go back 1 directory level (for fast typers)
alias ..='cd ../'                           # Go back 1 directory level
alias ...='cd ../../'                       # Go back 2 directory levels
alias .3='cd ../../../'                     # Go back 3 directory levels
alias c='clear'                             # c:            Clear terminal display

set completion-ignore-case on
export CC=gcc-4.2
# If not running interactively, don't do anything
[ -z "$PS1" ] && return

#osx color terminal
export CLICOLOR=1
export LSCOLORS=DxGxcxdxCxegedabagacad
# don't put duplicate lines in the history. See bash(1) for more options
# don't overwrite GNU Midnight Commander's setting of `ignorespace'.
HISTCONTROL=$HISTCONTROL${HISTCONTROL+,}ignoredups
# ... or force ignoredups and ignorespace
HISTCONTROL=ignoreboth

# append to the history file, don't overwrite it
shopt -s histappend
# check the window size after each command and, if necessary,
# update the values of LINES and COLUMNS.
shopt -s checkwinsize

# make less more friendly for non-text input files, see lesspipe(1)
[ -x /usr/bin/lesspipe ] && eval "$(SHELL=/bin/sh lesspipe)"

# set variable identifying the chroot you work in (used in the prompt below)
if [ -z "$debian_chroot" ] && [ -r /etc/debian_chroot ]; then
    debian_chroot=$(cat /etc/debian_chroot)
fi

#PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
PS1='\[\033[01;31m\]\w\[\033[00m\]\n${debian_chroot:+($debian_chroot)}\[\033[01;34m\]\u\[\033[01;32m\]@\[\033[01;34m\]\h\[\033[00m\]\$ '

# If this is an xterm set the title to user@host:dir
case "$TERM" in
xterm*|rxvt*)
    PS1="\[\e]0;${debian_chroot:+($debian_chroot)}\u@\h: \w\a\]$PS1"
    ;;
*)
    ;;
esac


# Set up TERM variables.
# vt100 and xterm have no color in vim (at least on unixs), but if we call them xterm-color, they will.
# (vt100 for F-Secure SSH.)
# This may well be the case for some other terms, so I'm putting them here.
# Also set up a variable to indicate whether to set up the title functions.
# TODO gnome-terminal, or however it reports itself
case $TERM in

  screen)
    TERM_IS_COLOR=true
    TERM_NOT_RECOGNIZED_AS_COLOR_BY_VIM=false
    TERM_NOT_RECOGNIZED_BY_SUN_UTILS=false
    TERM_CAN_TITLE=true
  ;;

  xterm-color|color_xterm|rxvt|Eterm|screen*) # screen.linux|screen-w
    TERM_IS_COLOR=true
    TERM_NOT_RECOGNIZED_AS_COLOR_BY_VIM=false
    TERM_NOT_RECOGNIZED_BY_SUN_UTILS=true
    TERM_CAN_TITLE=true
  ;;

  linux)
    TERM_IS_COLOR=true
    TERM_NOT_RECOGNIZED_AS_COLOR_BY_VIM=false
    TERM_NOT_RECOGNIZED_BY_SUN_UTILS=true
    TERM_CAN_TITLE=false
  ;;

  xterm|vt100)
    TERM_IS_COLOR=true
    TERM_NOT_RECOGNIZED_AS_COLOR_BY_VIM=true
    TERM_NOT_RECOGNIZED_BY_SUN_UTILS=false
    TERM_CAN_TITLE=true
  ;;

  *xterm*|eterm|rxvt*)
    TERM_IS_COLOR=true
    TERM_NOT_RECOGNIZED_AS_COLOR_BY_VIM=true
    TERM_NOT_RECOGNIZED_BY_SUN_UTILS=true
    TERM_CAN_TITLE=true
  ;;

  *)
    TERM_IS_COLOR=false
    TERM_NOT_RECOGNIZED_AS_COLOR_BY_VIM=false
    TERM_NOT_RECOGNIZED_BY_SUN_UTILS=false
    TERM_CAN_TITLE=false
  ;;

esac

# dircolors... make sure that we have a color terminal, dircolors exists, and ls supports it.
if $TERM_IS_COLOR && ( dircolors --help && ls --color ) &> /dev/null; then
  # For some reason, the unixs machines need me to use $HOME instead of ~
  # List files from highest priority to lowest.  As soon as the loop finds one that works, it will exit.
  for POSSIBLE_DIR_COLORS in "$HOME/.dir_colors" "/etc/DIR_COLORS"; do
    [[ -f "$POSSIBLE_DIR_COLORS" ]] && [[ -r "$POSSIBLE_DIR_COLORS" ]] && eval `dircolors -b "$POSSIBLE_DIR_COLORS"` && break
  done

  alias ls="ls --color=auto"
  alias ll="ls --color=auto -l"
  alias grep='grep --color=auto'
  alias fgrep='fgrep --color=auto'
  alias egrep='egrep --color=auto'
else
  # No color, so put a slash at the end of directory names, etc. to differentiate.
  alias ls="ls -F"
  alias ll="ls -lF"
fi

# Alias definitions.
if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi

# enable programmable completion features (you don't need to enable
# this, if it's already enabled in /etc/bash.bashrc and /etc/profile
# sources /etc/bash.bashrc).
if [ -f /etc/bash_completion ] && ! shopt -oq posix; then
    . /etc/bash_completion
fi
# Set $TERM for libvte terminals that set $TERM wrong (like gnome-terminal)
{
  [ "_$TERM" = "_xterm" ] && type ldd && type grep && type tput && [ -L "/proc/$PPID/exe" ] && {
    if ldd /proc/$PPID/exe | grep libvte; then
      if [ "`tput -Txterm-256color colors`" = "256" ]; then
        TERM=xterm-256color
      elif [ "`tput -Txterm-256color colors`" = "256" ]; then
        TERM=xterm-256color
      elif tput -T xterm; then
        TERM=xterm
      fi
    fi
  }
} >/dev/null 2>/dev/null

venwrap=`type -P virtualenvwrapper.sh`
if [ "$venwrap" != "" ]; then
    source $venwrap
fi

vim=`type -P vim`
if [ "$vim" == "" ]; then
    vim="gvim -v"
fi

alias vim="$vim"

alias la="ls -Al"

# osx vim
if [ -x "/Applications/MacVim.app/Contents/MacOS/Vim" ]; then
    PATH=/Applications/MacVim.app/Contents/MacOS/:$PATH
fi

#PYTHONSTARTUP=~/.pythonrc.py
#export PYTHONSTARTUP

parse_git_branch ()
{
  git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
parse_svn_branch() {
  parse_svn_url | sed -e 's#^'"$(parse_svn_repository_root)"'##g' | awk -F / '{print "(svn::"$1 "/" $2 ")"}'
}
parse_svn_url() {
  svn info 2>/dev/null | sed -ne 's#^URL: ##p'
}
parse_svn_repository_root() {
  svn info 2>/dev/null | sed -ne 's#^Repository Root: ##p'
}
set -o emacs
export EDITOR="$vim"
export GIT_EDITOR="$vim"

# Add git and svn branch names
export PS1="$PS1\$(parse_git_branch)\$(parse_svn_branch) "

'''









