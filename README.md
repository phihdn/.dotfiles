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

### Ref:

- [The best way to store your dotfiles: A bare Git repository](https://www.atlassian.com/git/tutorials/dotfiles)
- [The best way to store your dotfiles: A bare Git repository **EXPLAINED**](https://www.ackama.com/blog/posts/the-best-way-to-store-your-dotfiles-a-bare-git-repository-explained)
