fzf-ex is a command-line fuzzy finder for all module names in an Elixir Mix project. It's powered by [fzf](https://github.com/junegunn/fzf) and [bat](https://github.com/sharkdp/bat).

https://github.com/hauntedhost/fzf-ex/assets/81008/b7611b23-9998-4ef2-be00-2023074c9056

## Installation

1. Ensure that [fzf](https://github.com/junegunn/fzf) and [bat](https://github.com/sharkdp/bat) are installed:
   ```
   brew install fzf bat
   ```
2. Clone repo to `~/.fzf-ex`
   ```shell
   git clone https://github.com/hauntedhost/fzf-ex.git ~/.fzf-ex
   ```
3. Add PATH to `.zshrc` or `.bashrc`, etc
   ```shell
   PATH="~/.fzf-ex:$PATH"
   ```
4. (Optional) Bind CTRL+S to launch search
   ```shell
   # ~/.zshrc
   run-fzf-ex() {
     echo ""
     fzf-ex
     echo "\n"
     zle reset-prompt
   }
   zle -N run-fzf-ex
   bindkey '^S' run-fzf-ex
   ```

   ```shell
   # ~/.bashrc (untested)
   run_fzf_ex() {
     echo ""
     fzf-ex
     echo -e "\n"
     PS1="$PS1"
   }
   bind -x '"\C-s": run_fzf_ex'
   ```

## Usage

In the root of any Elixir Mix project press your bind key from step #3 above, or manually run:

```shell
$ fzf-ex
```

On the first run it will create the index. After 24 hours it will prompt you to reindex. You can reindex manually anytime with:

```shell
$ fzf-index
```
