##### How to install

```
yay -Syu zsh 
```

##### Tips

1. install also zsh-autosuggestions e  zsh-completions
2. zsh-autosuggestions is needed for auto-suggestions and saves its .zsh file in ``` /usr/share/zsh/plugins/zsh-autosuggestions/ ``` . It explains the Auto-suggestion session in the .zshrc file below.
3. zsh don't save history by default, so we have to configure it in the .zshrc file, as seen below.
4. The default zsh prompt is not much useful, so I change it, as can be seen below too.
5. To define zsh as your default shell see [[Changing shell]]  

##### .zshrc file

```
# Created by newuser for 5.9

# Prompt

PROMPT='%F{blue}%5~ %#%f ' 

# Autocompletion

autoload -Uz compinit
compinit

zstyle ':completion:*' menu select
zstyle ':completion::complete:*' gain-privileges 1

# History search

autoload -Uz up-line-or-beginning-search down-line-or-beginning-search
zle -N up-line-or-beginning-search
zle -N down-line-or-beginning-search

[[ -n "${key[Up]}"   ]] && bindkey -- "${key[Up]}"   up-line-or-beginning-search
[[ -n "${key[Down]}" ]] && bindkey -- "${key[Down]}" down-line-or-beginning-search

# Auto-suggestion

source /usr/share/zsh/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh

# Save history

HISTFILE=~/.histfile
HISTSIZE=1000
SAVEHIST=1000
setopt appendhistory
``` 

##### Relevant texts
1. [Customizing the zsh prompt ](https://scriptingosx.com/2019/07/moving-to-zsh-06-customizing-the-zsh-prompt/)
2. [Arch Wiki's zsh article](https://wiki.archlinux.org/title/zsh)
