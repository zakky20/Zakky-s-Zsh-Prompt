# Zakky's Zsh Prompt

# This is a prompt created by me with the features i need and i like.

# This is how it looks: 

<img width="317" height="55" alt="prompt" src="https://github.com/user-attachments/assets/04baf3ae-dd40-4f9f-b4f4-59f95cee8b8b" />

to apply it to your .zshrc file u need to copy this:

```
autoload -U colors && colors
autoload -Uz vcs_info

MAGENTA="%B%F{red}"
WHITE="%B%F{white}"
ORANGE="%B%F{166}"
GREEN="%B%F{190}"
PURPLE="%B%F{141}"
RESET="%f%b"

zstyle ':vcs_info:git:*' formats '%b'
zstyle ':vcs_info:*' enable git
precmd() { vcs_info }  # Refresh git info before each prompt

virtualenv_info() {
  [[ -n "$VIRTUAL_ENV" ]] && echo "($(basename "$VIRTUAL_ENV")) "
}
conda_env_info() {
  [[ -n "$CONDA_DEFAULT_ENV" ]] && echo "($(basename "$CONDA_DEFAULT_ENV")) "
}

PROMPT='$(virtualenv_info)$(conda_env_info)'$PURPLE' %n '$WHITE'@ '$PURPLE'%m  '$RESET'in '$PURPLE' '$WHITE'%~ '$WHITE'| '$PURPLE'󰥔 %D{%H:%M:%S} '$PURPLE'$vcs_info_msg_0_'$WHITE'
'$WHITE'$ '
