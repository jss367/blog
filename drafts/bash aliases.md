bash aliases


function to reach out to an ec2 instance:

function s () {
	ssh jsimonelli@host${1:0:1}pu10${1:1:3}.network.domain.tld
}


alias ff='find . -name'
findpy='find . -name "*.py" | xargs grep --color'
grep='grep --color=auto'
hgrep='history | grep -v grep | grep '
ll='ls -GlAFh'
lls='ls -GlAFhS'
..='cd..'
...='cd../..'



gs='git status'

#redo last command but with sudo
please='sudo $(history -p !!)'

wgpu='watch -d -n 0.5 nvidia-smi'
ns='watch -d -n 0.5 nvidia-htop.py'


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


 