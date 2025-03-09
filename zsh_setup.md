# Configuration de Zsh et Oh My Zsh

## 1. Installation de Zsh

Tout d'abord, vérifier si **Zsh** est installé :

```sh
zsh --version
```

Si ce n'est pas le cas, l'installer avec :

```sh
sudo apt install zsh
```

Ensuite, pour utiliser **Zsh** comme shell par défaut :

```sh
sudo chsh -s $(which zsh)
```

🔹 **Explication** :  
- `chsh -s` permet de changer le shell par défaut.  
- `which zsh` renvoie le chemin vers l'exécutable de **Zsh**.

Ouvrir un **nouveau terminal** et vérifier que **Zsh** est bien utilisé par défaut :

```sh
echo $SHELL
```

Si tout est correct, cela doit renvoyer `/bin/zsh`.

---

## 2. Installation de Oh My Zsh

Oh My Zsh est un framework de gestion de configuration pour **Zsh**, qui ajoute de nombreuses fonctionnalités et personnalisations.

Installation via **cURL** :

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Ou via **Wget** :

```sh
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Une fois installé, **Oh My Zsh** est actif.

---

## 3. Personnalisation de Zsh

### 3.1. Installation de plugins

Cloner les plugins dans le dossier de **Oh My Zsh** :

```sh
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
git clone https://github.com/MichaelAquilina/zsh-you-should-use.git ~/.oh-my-zsh/custom/plugins/you-should-use
```

### 3.2. Modification du fichier `.zshrc`

Éditer le fichier de configuration **Zsh** :

```sh
nano ~/.zshrc
```

Puis modifier ces lignes (ou les ajouter si absentes) :

```sh
export ZSH="$HOME/.oh-my-zsh"
ZSH_THEME="robbyrussell"

plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
  you-should-use
)

source $ZSH/oh-my-zsh.sh
```

### 3.3. Appliquer les changements

Après modification du fichier `.zshrc`, appliquer les changements en exécutant :

```sh
source ~/.zshrc
```

---

## 4. Vérification de la configuration

Tester si **Oh My Zsh** et les plugins fonctionnent correctement :

- **Autosuggestions** : taper une commande et observer les suggestions en gris.  
- **Syntax Highlighting** : taper une commande incorrecte et voir si elle s'affiche en rouge.  
- **You Should Use** : taper `git pull` et voir si des suggestions apparaissent.  
