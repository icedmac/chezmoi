# 🚀 Dotfiles avec chezmoi

Ce dépôt contient ma configuration personnelle gérée avec [chezmoi](https://www.chezmoi.io).

## Ce que ça installe

- **Paquets de base** : zsh, git, curl, unzip, zip, fzf…
- **oh-my-zsh** avec plugins :
  - zsh-autosuggestions
  - zsh-syntax-highlighting
- **Thème** : [powerlevel10k](https://github.com/romkatv/powerlevel10k)
- **Node.js** via [nvm](https://github.com/nvm-sh/nvm) (version 22 + npm)
- **npm global** :  
  - `@anthropic-ai/claude-code`  
- **Dotfiles** : `.zshrc`, `.p10k.zsh`

---

## 🔧 Installation sur une nouvelle machine

```bash
# 1. Installer chezmoi
sh -c "$(curl -fsLS get.chezmoi.io)" -- -b "$HOME/.local/bin"
export PATH="$HOME/.local/bin:$PATH"

# 2. Initialiser avec mon dépôt
chezmoi init https://github.com/icedmac/chezmoi.git

# 3. Appliquer la configuration
chezmoi apply -v
```

---

## 📘 Usage quotidien

- Modifier un fichier géré :
  ```bash
  chezmoi edit ~/.zshrc
  ```

- Ajouter un nouveau fichier :
  ```bash
  chezmoi add ~/.nouveau_fichier
  ```

- Voir les différences :
  ```bash
  chezmoi diff
  ```

- Synchroniser avec GitHub :
  ```bash
  cd ~/.local/share/chezmoi
  git add .
  git commit -m "update config"
  git push
  ```

