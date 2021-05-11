# BASH WITH GIT BRANCHES
Configurations for .bashrc file to shows git branches and colors

### HOW TO
Open .bashrc file and paste/replace:

```sh
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}

if [ "$color_prompt" = yes ]; 
    PS1='\n${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]: \[\033[01;34m\]\w \[\e[91m\]$(parse_git_branch)\n\[\e[00m\]$ '
```

Then your terminal will look like this:

```sh
user@host: /folder (branch)
$
```

😉

For more details, see [How to show current git branch with colors in Bash prompt](https://medium.com/@thucnc/how-to-show-current-git-branch-with-colors-in-bash-prompt-380d05a24745)
