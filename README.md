# starter-template

Template de démarrage pour la documentation, les templates et la génération du CSS. Ce dépôt est un clone de [Jekyll LibDoc](https://olivier3lanc.github.io/Jekyll-LibDoc/) personnalisé pour ITADS.

## Rôle du starter-template

* **Créer les templates** du projet avec son environnement complet (générique + personnalisé) du système de design IT Automotive.
* **Créer la documentation des extensions de composants**, la documentation qui n'est pas incluse dans la documentation des composants génériques.

## Installation locale avec Jekyll LibDoc distant

1. Cloner ce dépôt.
2. Installer Jekyll sur votre machine en suivant les [instructions](https://jekyllrb.com/docs/)
3. Ajouter un Gemfile contenant la ligne suivante

  ```ruby
  gem "jekyll-remote-theme"
  ```
  et exécuter `bundle install` pour installer le plugin.
4. Ajouter les lignes suivantes dans votre fichier de configuration LibDoc `_<NOM DU FICHIER>.yml`

  ```yml
  remote_theme: ita-design-system/jekyll-libdoc
  plugins:
    - jekyll-remote-theme
  ```
5. Exécuter `jekyll build` ou `jekyll build -c _votre-fichier-config.yml`
