## Storing dot files

```sh
git init --bare $HOME/.dotfiles
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles config --local status.showUntrackedFiles no
echo "alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'" >> $HOME/.zsh/aliases
```

```sh
dotfiles add .zshrc
dotfiles commit -m "add .zshrc"

dotfiles remote add origin git@github.com:phihdn/.dotfiles.git
dotfiles push -u origin master
```

## Installing

```sh
echo ".dotfiles" >> .gitignore
git clone --bare git@github.com:phihdn/.dotfiles.git $HOME/.dotfiles
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles config --local status.showUntrackedFiles no
dotfiles checkout
```
