# Ajouter des fonctionnalités à Git Bash sur Windows

L'idée de base est que `C:\Program Files\Git\mingw64\` est votre répertoire racine `/` selon Git Bash (*note*: selon la manière dont il a était installé, le répertoire pourrait être différent. À partir du menu Démarrer, cliquez avec le bouton droit sur l'icône de Git Bash et ouvrez l'emplacement du fichier. Il pourrait ressembler à `C:\Users\name\AppData\Local\Programs\Git`, le `mingw64` dans ce répertoire est votre racine. Trouvez-le en utilisant `pwd -W`).
Si vous accédez à ce répertoire, vous trouverez la structure typique du répertoire racine de Linux (`bin`, `etc`, `lib`, etc...). 

Si vous manquez d'un utilitaire, tel que wget, cherchez un binaire pour Windows et copiez les fichiers dans les répertoires correspondants.
Parfois, les binaires Windows ont des préfixes incorrect/inadéquat, vous devez donc **renommer** le fichier `.exe` avec un nom standard.
Comme `bin` est sur le PATH, il sera automatiquement disponible pour Git Bash.

*Note:* De nombreux utilitaires interactifs, tels que `python`, `ipython` ou `nano`, ne s'affichent pas correctement avec le terminal mintty de Git Bash.
Essayez de les invoquer avec `winpty` à la place, par exemple `winpty ipython` fonctionnera bien.


# Liste d'utilitaires à ajouter:

## Wget 

- Téléchargez le dernier binaire de wget pour Windows à partir de [eternallybored](https://eternallybored.org/misc/wget/) (ils sont disponibles sous forme de zip avec de la documentation, ou simplement en tant qu'exécutable)
- Si vous avez téléchargé le zip, extrayez tout (si l'utilitaire de zip intégré de Windows donne une erreur, utilisez [7-zip](http://www.7-zip.org/)).
- Renommez le fichier `wget64.exe` en `wget.exe` si nécessaire.
- Déplacez `wget.exe` dans votre `Git\mingw64\bin\`.

## Hugo 

Le générateur de site statique [Hugo](http://gohugo.io/) peut être téléchargé sous forme de binaire et n'a pas d'installateur. 
Il suffit de le déposer dans votre dossier bin pour l'ajouter facilement à votre chemin Git Bash. 
Obtenez la version Windows 64 bits depuis la page de [téléchargement](https://github.com/gohugoio/hugo/releases). 
Décompressez le fichier, puis copiez `hugo.exe` dans votre répertoire `Git\mingw64\bin`.

## Xpdf

[Xpdf](http://www.xpdfreader.com/index.html) est un utilitaire pratique pour manipuler des fichiers PDF.

- Téléchargez la version Windows de ["Xpdf tools"](http://www.xpdfreader.com/download.html).
- Décompressez le fichier zip.
- Copiez le contenu de `xpdf-tools-win-4.00\bin64\` dans le répertoire `Git\mingw64\bin\`.
- Consultez la [docs](http://www.xpdfreader.com/support.html) pour commencer à utiliser des outils tels que `pdftotext` et `pdftopng`.

## ExifTool

- Téléchargez l'"exécutable Windows autonome" depuis la page [ExifTool](https://exiftool.org/) (ce sera un fichier `.zip` comme "exiftool-11.99.zip").
- Décompressez le fichier zip.
- À l'intérieur, vous trouverez un fichier nommé `exiftool(-k).exe`. Renommez-le en `exiftool.exe`.
- Déplacez `exiftool.exe` dans votre répertoire `Git\mingw64\bin\`.

## Autres possibilités

La plupart des utilitaires qui fournissent des versions binaires pour Windows peuvent être ajoutés à GitBash en suivant le même schéma. 
Voici quelques exemples pratiques :

- [jq](https://github.com/stedolan/jq/releases)
- [htmlq](https://github.com/mgdm/htmlq/releases)

## make (Makefile)

> Gardez à l'esprit que vous pouvez facilement ajouter `make`, mais il ne vient pas empaqueté avec toute la chaîne d'outils de construction UNIX standard, vous devrez donc vous assurer que ceux-ci sont installés *et* avoir le bon PATH, ou vous rencontrerez des messages d'erreur sans fin.

- Allez sur [ezwinports](https://sourceforge.net/projects/ezwinports/files/).
- Téléchargez `make-4.4.1-without-guile-w32-bin.zip` (Choisir la version sans guile).
- Décompressez le fichier zip.
- Copiez le contenu dans le répertoire `Git\mingw64\` en fusionnant les dossiers/fichiers, mais *NE SURTOUT PAS* remplacez les fichiers existants. 

## Nano

> Normalement les versions récentes de Git Bash incluent Nano, il n'est donc pas nécessaire de télécharger Nano ! Assurez-vous simplement de choisir Nano comme éditeur par défaut lors de l'installation de Git pour Windows.

- Téléchargez le binaire Nano à partir de la page de support [win32-support](https://www.nano-editor.org/dist/win32-support/). Vous n'avez besoin que du fichier `.exe`, qui est nommé `nano-git-0d9a7347243.exe`.
- Renommez le fichier en `nano.exe`, et copiez-le dans le dossier `mingw64\bin`.
- Cette version de Nano ne fonctionnera pas seul avec Git Bash, mais elle peut être appelée en utilisant `winpty`, par exemple, `winpty nano test.txt`.
