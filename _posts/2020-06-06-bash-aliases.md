folder structure:

.bash_alias

.bash_variables?

.profile?

how does .bashrc call these?

bash aliases



```
alias ff='find . -name'
findpy='find . -name "*.py" | xargs grep --color'
grep='grep --color=auto'
hgrep='history | grep -v grep | grep '
ll='ls -GlAFh'
lls='ls -GlAFhS'
..='cd..'
...='cd../..'
```

```
gs='git status'

#redo last command but with sudo
please='sudo $(history -p !!)'

wgpu='watch -d -n 0.5 gpustat' # requires gpustat
ns='watch -d -n 0.5 nvidia-htop.py

nb='jupyter notebook --port=8888 --no-browser --ip=0.0.0.0 ==allow-root --NotebookApp.iopub_data_rate_limit=1000000000'


#useful functions
function cheat() {
 curl cht.sh/$1
 }

function extract () {
 if [ -f $1 ] ; then
 case $1 in
 *.tar.bz2) tar xjf $1 ;;
 *.tar.gz) tar xzf $1 ;;
 *.bz2) bunzip2 $1 ;;
 *.rar) unrar e $1 ;;
 *.gz) gunzip $1 ;;
 *.tar) tar xf $1 ;;
 *.tbz2) tar xjf $1 ;;
 *.tgz) tar xzf $1 ;;
 *.zip) unzip $1 ;;
 *.Z) uncompress $1 ;;
 *.7z) 7z x $1 ;;
 *) echo "'$1' cannot be extracted via extract()" ;;
 esac
 else
 echo "'$1' is not a valid file"
 fi
 }
```

```
# reload user profile
alias rp='source ~/.profile'
alias rld='source ~/.bashrc' #reload

# better ls (column detail and no meta-files (., .., etc))
alias ls='ls -lA'

alias showpath='echo $PATH | tr ":" "\n"'
```

conda activate "$DEFAULT_CONDA_ENVIRONMENT"
 
color git branch:
```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
export PS1="\u@\h \[\e[32m\]\w \[\e[91m\]\$(parse_git_branch)\[\e[00m\]$ "
```

```
# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi
```

```
# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
```

## Oh My Zsh

I recommend people use [Oh My Zsh](https://ohmyz.sh/)

```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
# customize the zsh prompt
PS1='%B%F{green}%(?.%F{green}√.%F{red}X:%?) %B%F{251} %1~ $(parse_git_branch)\ %# '
```

I usually leave the theme as `ZSH_THEME="robbyrussell"`


Then I put my profile in `~/.oh-my-zsh/custom/profile.zsh`





## Useful Git Commands

These are good to set to an alias

`git log --pretty=format:'%C(yellow)%h %Cred%ad %Cblue%an%Cgreen%d %Creset%s' --date=short`


Testing:
```
# set a fancy prompt (non-color, unless we know we "want" color)
case "$TERM" in
    xterm-color|*-256color) color_prompt=yes;;
esac
```

 
