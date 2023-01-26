# starter-template

Point de départ pour tout nouveau projet web utilisant le système de design de IT Automotive. Ce dépôt est un clone de [Jekyll LibDoc](https://olivier3lanc.github.io/Jekyll-LibDoc/) personnalisé pour ITADS.

```mermaid
classDiagram
    Jekyll_LibDoc <|-- Briks
    Briks <|-- Generic_Utilities
    Briks <|-- Generic_Components
    Briks <|-- Design_Tokens
    Starter_Template <|-- Jekyll_LibDoc
    Starter_Template <|-- UI_Files
    Starter_Template <|-- Components_Extensions
    Starter_Template <|-- Utilities_Extensions
    Starter_Template <|-- Templates
    Starter_Template <|-- Project_Documentation
    Generic_Components <|-- Design_Tokens
    Generic_Utilities <|-- Design_Tokens
    class Starter_Template {
        Point de départ nouveau projet web IT Automotive
        GitHub Pages
    }
    class Jekyll_LibDoc{
        Thème distant Jekyll
        Compilateur SASS
        Générateur documentation
    }
    class Project_Documentation {
        /content/doc
        Fichiers markdown ou html
    }
    class Templates {
        /content/templates
        Fichiers html Liquid
    }
    class Components_Extensions {
        _sass/_dis_extension
        _sass/_dim_extension
        _sass/_pos_extension
        _sass/_txt_extension
        _sass/_skin_extension
    }
    class Generic_Components {
        _dis_generic.scss
        _dim_generic.scss
        _pos_generic.scss
        _txt_generic.scss
        _skin_generic.scss
    }
    class Generic_Utilities {
        _utilities_generic.scss
    }
    class Utilities_Extensions {
        _utilities_extensions.scss
    }
    class Briks{
        CSS Framework
    }
    class Design_Tokens {
        colors
        screen_sizes
        font_families
        font_sizes
        spacings
        borders
        border_radius
        shadows
    }
    class UI_Files {
        /css
        /medias
        /js
    }
```

## Rôle du starter-template

* **Décrire les design tokens** à partir desquels toutes les compositions et templates sont créés.
* **Créer des extraits de code fonctionnels, appelés compositions** (boutons, modales, etc) à partir des composants génériques [c-dis](https://github.com/ita-design-system/c-dis.scss), [c-dim](https://github.com/ita-design-system/c-dim.scss), [c-pos](https://github.com/ita-design-system/c-pos.scss), [c-txt](https://github.com/ita-design-system/c-txt.scss), [c-skin](https://github.com/ita-design-system/c-skin.scss) et de leurs extensions.
* **Créer les templates** du projet accompagné de son environnement complet.
* **Créer la documentation** dédiée au projet.

## Codespaces

Ce projet peut être développé avec Github codespaces

<img width="453" alt="image" src="https://user-images.githubusercontent.com/13103047/211783775-55d429ec-45c6-4015-8cd4-6321dc041913.png">


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

## Démarrage

Le starter-template contient l'arborescence des fichiers:

```
ui/
├── css/
│   ├── briks_css_variables.scss
│   ├── briks_dim_extension.scss
│   ├── briks_dim_generic.scss
│   ├── briks_dis_extension.scss
│   ├── briks_dis_generic.scss
│   ├── briks_fonts.scss
│   ├── briks_pos_extension.scss
│   ├── briks_pos_generic.scss
│   ├── briks_skin_extension.scss
│   ├── briks_skin_generic.scss
│   ├── briks_txt_extension.scss
│   ├── briks_txt_generic.scss
│   ├── briks_utilities_generic.scss
│   └── briks_utilities_extension.scss
├── medias
└── js
```

## Scope des composants

Le diagramme ci-dessous reprend la portée des propriétés CSS des composants.

```mermaid
classDiagram
    class c_dis {
        display
        align-items
        justify-content
        flex-wrap
        flex-direction
        gap
        grid-gap
    }
    class c_dim {
        aspect-ratio
        flex-grow
        height
        margin
        max-height
        max-width
        min-height
        min-width
        order
        overflow
        padding
        width
    }
    class c_pos {
        position
        top
        right
        bottom
        left
        transform
        z-index
    }
    class c_txt {
        display: -webkit-box
        font-family
        font-size
        font-style
        font-weight
        letter-spacing
        line-height
        text-align
        text-decoration
        text-overflow
        text-transform
        vertical-align
        white-space
        word-break
        -webkit-box-orient
        -webkit-line-clamp
    }
    class c_skin {
        background
        border
        border-radius
        box-shadow
        color
        cursor
        list-style
        opacity
        outline
        pointer-events
        transition
    }
 ```
 
 ## Abréviations utilisées

Abréviations désignant les propriété CSS.

| Propriété CSS | Abréviation | Composant / modifieur associé | Utilitaire associé |
|:-|:-|:-|:-|
| aspect-ratio | `ar-` | `c-dim m-ar-` | `u-ar-` |
| background | `bg-` | `c-skin m-bg-` | `u-bg-` |
| background-color | `bc-` | `c-skin m-bc-` | `u-bc-` |
| background-image | `bi-` | `c-skin m-bi-` | `u-bi-` |
| background-position | `bpos-` | `c-skin m-bpos-` | `u-bpos-` |
| background-repeat | `brep-` | `c-skin m-brep-` | `u-brep-` |
| background-size | `bsize-` | `c-skin m-bsize-` | `u-bsize-` |
| border | `b-` | `c-skin m-b-` | `u-b-` |
| border-top | `bt-` | `c-skin m-bt-` | `u-bt-` |
| border-right | `br-` | `c-skin m-br-` | `u-br-` |
| border-bottom | `bb-` | `c-skin m-bb-` | `u-bb-` |
| border-left | `bl-` | `c-skin m-bl-` | `u-bl-` |
| border-radius | `brad-` | `c-skin m-brad-` | `u-brad-` |
| border-top-left-radius | `bradtl-` | `c-skin m-bradtl-` | `u-bradtl-` |
| border-top-right-radius | `bradtr-` | `c-skin m-bradtr-` | `u-bradtr-` |
| border-bottom-right-radius | `bradbr-` | `c-skin m-bradbr-` | `u-bradbr-` |
| border-bottom-left-radius | `bradbl-` | `c-skin m-bradbl-` | `u-bradbl-` |
| bottom | `bottom-` | `c-pos m-bottom-` | `u-bottom-` |
| box-shadow | `bs-` | `c-skin m-bs-` | `u-bs-` |
| color | `c-` | `c-skin m-c-` | `u-c-` |
| cursor | `cur-` | `c-skin m-cur-` | `u-cur-` |
| display | `d-` | `c-dis m-` | `u-d-` |
| font-family | `ff-` | `c-txt m-ff-` | `u-ff-` |
| font-size | `fs-` | `c-txt m-fs-` | `u-fs-` |
| font-style | `fstyle-` | `c-txt m-fstyle-` | `u-fstyle-` |
| font-weight | `fw-` | `c-txt m-fw-` | `u-fw-` |
| height | `h-` | `c-dim m-h-` | `u-h-` |
| left | `left-` | `c-pos m-left-` | `u-left-` |
| letter-spacing | `lsp-` | `c-txt m-lsp-` | `u-lsp-` |
| line-height | `lh-` | `c-txt m-lh-` | `u-lh-` |
| list-style | `ls-` | `c-skin m-ls-` | `u-ls-` |
| margin | `m-` | `c-dim m-m-` | `u-m-` |
| margin-top | `mt-` | `c-dim m-mt-` | `u-mt-` |
| margin-right | `mr-` | `c-dim m-mr-` | `u-mr-` |
| margin-bottom | `mb-` | `c-dim m-mb-` | `u-mb-` |
| margin-left | `ml-` | `c-dim m-ml-` | `u-ml-` |
| max-height | `maxh-` | `c-dim m-maxh-` | `u-maxh-` |
| max-width | `maxw-` | `c-dim m-maxw-` | `u-maxw-` |
| min-height | `minh-` | `c-dim m-minh-` | `u-minh-` |
| min-width | `minw-` | `c-dim m-minw-` | `u-minw-` |
| opacity | `opa-` | `c-skin m-opa-` | `u-opa-` |
| order | `order-` | `c-dim m-order-` | `u-order-` |
| overflow | `o-` | `c-dim m-o-` | `u-o-` |
| padding | `p-` | `c-dim m-p-` | `u-p-` |
| padding-top | `pt-` | `c-dim m-pt-` | `u-pt-` |
| padding-right | `pr-` | `c-dim m-pr-` | `u-pr-` |
| padding-bottom | `pb-` | `c-dim m-pb-` | `u-pb-` |
| padding-left | `pl-` | `c-dim m-pl-` | `u-pl-` |
| pointer-events | `pe-` | `c-skin m-pe-` | `u-pe-` |
| right | `right-` | `c-pos m-right-` | `u-right-` |
| text-align | `ta-` | `c-txt m-ta-` | `u-ta-` |
| text-decoration | `td-` | `c-txt m-td-` | `u-td-` |
| text-transform | `tt-` | `c-txt m-tt-` | `u-tt-` |
| transition | `transition-` | `c-skin m-transition-` | `u-transition-` |
| top | `top-` | `c-pos m-top-` | `u-top-` |
| vertical-align | `va-` | `c-txt m-va-` | `u-va-` |
| visibility | `v-` | `c-skin m-v-` | `u-v-` |
| word-break | `wb-` | `c-txt m-wb-` | `u-wb-` |
| white-space | `ws-` | `c-txt m-ws-` | `u-ws-` |
| width | `w-` | `c-dim m-w-` | `u-w-` |
| z-index | `z-` | `c-pos m-z-` | `u-z-` |
