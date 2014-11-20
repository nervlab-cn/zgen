zgen
====

A light plugin manager for zsh inspired by Antigen.

## Usage

`zgen oh-my-zsh` clone and run oh-my-zsh

`zgen load <github repo> <script>` clone the repo and run the script

`zgen save` save all loaded scripts into an init script so they'll get run each time you source zgen

`zgen update` update all repositories

## Example .zshrc using init script

```zsh
# load zgen
source "${HOME}/proj/zgen/zgen.zsh"

# check if there's an init script
if [[ ! -f "${ZGEN_INIT}" ]]; then
    echo "no init script found; creating one"

    zgen oh-my-zsh

    # plugins
    zgen load robbyrussell/oh-my-zsh plugins/git/git.plugin.zsh
    zgen load robbyrussell/oh-my-zsh plugins/npm/npm.plugin.zsh
    zgen load robbyrussell/oh-my-zsh plugins/pip/pip.plugin.zsh
    zgen load robbyrussell/oh-my-zsh plugins/command-not-found/command-not-found.plugin.zsh
    zgen load robbyrussell/oh-my-zsh plugins/sudo/sudo.plugin.zsh
    zgen load zsh-users/zsh-syntax-highlighting zsh-syntax-highlighting.zsh

    # theme
    zgen load robbyrussell/oh-my-zsh themes/arrow.zsh-theme

    # save all to init script
    zgen save
fi
```
You don't have to check init script's existance but doing so makes startup faster ;)
