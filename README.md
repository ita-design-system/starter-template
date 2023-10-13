# starter-template

Point de départ pour tout nouveau projet web utilisant le système de design de IT Automotive. Ce dépôt est un clone de [Jekyll LibDoc](https://olivier3lanc.github.io/Jekyll-LibDoc/) personnalisé pour ITADS. 

## Rôle du starter-template

* **Décrire les design tokens** à partir desquels toutes les compositions et templates sont créés.
* **Créer des extraits de code fonctionnels, appelés compositions** (boutons, modales, etc) à partir des composants génériques [c-dis](https://github.com/ita-design-system/c-dis.scss), [c-dim](https://github.com/ita-design-system/c-dim.scss), [c-pos](https://github.com/ita-design-system/c-pos.scss), [c-txt](https://github.com/ita-design-system/c-txt.scss), [c-skin](https://github.com/ita-design-system/c-skin.scss) et de leurs extensions.
* **Créer les templates** du projet accompagné de son environnement complet.
* **Créer la documentation** dédiée au projet.


## Installation

1. Créer un nouveau fichier avec les design tokens dans le répertoire du dépôt [jekyll-libdoc/_sass/briks/settings/tokens](https://github.com/ita-design-system/jekyll-libdoc/tree/main/_sass/briks/settings/tokens). Pour plus de facilités, "enregister sous" le fichier `_generic.scss` et renseigner les maps SCSS.
2. [Installer en local](#installation-locale-avec-jekyll-libdoc-distant) ou créer un nouveau codespaces. Pour l'installation locale avec Jekyll LibDoc distant:
    1. Cloner ce dépôt.
    2. Installer Jekyll sur votre machine en suivant les [instructions](https://jekyllrb.com/docs/)
    3. Si le gem jekyll-remote-theme n'est pas déjà installé sur la machine, exécuter `bundle install` pour l'installer.
    4. Ouvrir le fichier `_config.yml` et l'enregistrer sous `_config-ip.yml` (_config-ip.yml est présent dans .gitignore et ne doit pas être répertorié dans git)
    5. Renseigner les champs du fichier _config-ip.yml:
        1. `title` le nom du projet.
        2. `description` la description du projet.
        3. `url` l'URL locale, par exemple "http://192.168.1.6" ou "http://localhost" etc
        4. `baseurl` le chemin vers le dossier cible, par exemple "/starter-template/_site".
    6. Renseigner les champs du fichier _config.yml dédié à la configuration [Github Pages](https://pages.github.com/) du projet
        1. `title` le nom du projet (idem que _config-ip.yml).
        2. `description` la description du projet (idem que _config-ip.yml).
        3. `url` et `baseurl` doivent rester commentées.
    7. Exécuter `jekyll build -c _config-ip.yml`. Par défaut, le site est généré dans le répertoire `_site` dans le répertoire du dépôt.


### Points d'entrées SASS

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
├── fonts
├── medias
└── js
```

```mermaid
classDiagram
    Starter_Template <|-- Components_Extensions
    Starter_Template <|-- Utilities_Extensions
    Starter_Template <|-- Templates
    Starter_Template <|-- Project_Documentation
    Starter_Template <|-- Points_d_entrees
    class Starter_Template {
        Point de départ nouveau projet web IT Automotive
        GitHub Pages
    }
    class Points_d_entrees {
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
        ├── fonts
        ├── medias
        └── js
    }
    class Project_Documentation {
        content/
        └── doc/
            ├── 1.colors.html
            ├── 2.screen-sizes.html
            ├── 3.font-families.html
            ├── 4.font-sizes.html
            ├── 5.spacings.html
            ├── 6.borders.html
            ├── 7.border-radii.html
            ├── 8.shadows.html
            ├── button.html
            ├── checkbox.html
            ├── containers.html
            ├── details.html
            ├── input.html
            ├── modal.html
            ├── radio.html
            ├── select.html
            └── ...
    }
    class Templates {
        content/
        └── templates/
            ├── homepage.html
            ├── contact.html
            ├── page_file.html
            ├── page_file.html
            └── ...
    }
    class Components_Extensions {
        _sass/_dis_extension
        _sass/_dim_extension
        _sass/_pos_extension
        _sass/_txt_extension
        _sass/_skin_extension
    }
    class Utilities_Extensions {
        _utilities_extensions.scss
    }
```

```mermaid
classDiagram
    Jekyll_LibDoc <|-- Briks
    Briks <|-- Generic_Utilities
    Briks <|-- Generic_Components
    Briks <|-- Design_Tokens
    Generic_Components <|-- Design_Tokens
    Generic_Utilities <|-- Design_Tokens
    class Jekyll_LibDoc{
        Thème distant Jekyll
        Compilateur SASS
        Générateur documentation
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
    class Briks{
        CSS Framework
    }
    class Design_Tokens {
        colors
        screen_sizes
        font_families
        font_sizes
        spacings
        border_radius
        shadows
    }
```




# ITADS

Présentation et généralités du système de design de IT Automotive

## C'est quoi un Design System ?

> Développer des sites et applications en utilisant des composants prêts à l'emploi, accessibles et ergonomiques <br><sub>[Source : Système de Design du Gouvernement](https://www.systeme-de-design.gouv.fr/)</sub>

Des exemples de Design Systems [https://designsystemsrepo.com/](https://designsystemsrepo.com/)

## [CSS] Généralités

Le framework UI CSS s'appelle **briks.scss** et permet de générer des fichiers composants CSS. Les composants CSS sont placés dans des dépôts indépendants à partir de l'organisation [ITADS](https://github.com/orgs/ita-design-system/)

### [CSS] Méthodologie

La méthodologie utilisée est une hybridation de [Atomic Design](https://bradfrost.com/blog/post/atomic-web-design/), [BEM](https://getbem.com/) comme [Bootstrap](https://getbootstrap.com/) et Utility first comme [Tailwind.css](https://tailwindcss.com/). Les grands principes sont :

* **Pas de HTML associé** : chaque classe CSS n'est associée ni à une balise, ni à une arborescence HTML. 
* **Pas d'héritage** : Sauf exceptions, les sélecteurs n'utilisent pas l'héritage mais affectent uniquement les propriétés de l'élément spécifié.

### [CSS] Composant

Un composant `c-` est une classe CSS qui contient zéro ou plusieurs propriétés CSS. Le composant peut affecter des [pseudo-classes](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-classes) et des [pseudo-éléments](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-elements). Le nom de cette classe est composé d'un préfixe et d'un nom, souvent abrégé, qui désigne une fonctionnalité. Exemples : 
* `c-txt` nom de la classe CSS du composant c-txt.
  * `c-` : préfixe composant.
  * `txt` : nom du composant dédié au texte.
* `c-skin` nom de la classe CSS du composant c-skin.
  * `c-` : préfixe composant.
  * `skin` : nom du composant dédié aux aspects et apparences.

### [CSS] Scope

Portée des composants sur les propriétés CSS:

<details>
    <summary><strong>Scope c-dis</strong></summary>
    <ul>
        <li>align-items</li>
        <li>backface-visibility</li>
        <li>clear</li>
        <li>display</li>
        <li>justify-content</li>
        <li>flex</li>
        <li>flex-basis</li>
        <li>flex-direction</li>
        <li>flex-flow</li>
        <li>flex-shrink</li>
        <li>flex-wrap</li>
        <li>float</li>
        <li>gap</li>
        <li>grid-gap</li>
        <li>grid</li>
        <li>grid-area</li>
        <li>grid-auto-columns</li>
        <li>grid-auto-flow</li>
        <li>grid-auto-rows</li>
        <li>grid-column</li>
        <li>grid-column-end</li>
        <li>grid-column-start</li>
        <li>grid-row</li>
        <li>grid-row-end</li>
        <li>grid-row-start</li>
        <li>grid-template</li>
        <li>grid-template-areas</li>
        <li>grid-template-columns</li>
        <li>grid-template-rows</li>
        <li>row-gap</li>
        <li>place-content</li>
        <li>place-items</li>
        <li>place-self</li>
        <li>table-layout</li>
        <li>visibility</li>
        <li>-webkit-box-orient</li>
        <li>-webkit-line-clamp</li>
    </ul>
</details>
<details>
    <summary><strong>Scope c-dim</strong></summary>
    <ul>
        <li>align-self</li>
        <li>aspect-ratio</li>
        <li>box-sizing</li>
        <li>flex-grow</li>
        <li>height</li>
        <li>justify-self</li>
        <li>margin</li>
        <li>margin-block</li>
        <li>margin-block-end</li>
        <li>margin-block-start</li>
        <li>margin-bottom</li>
        <li>margin-inline</li>
        <li>margin-inline-end</li>
        <li>margin-inline-start</li>
        <li>margin-left</li>
        <li>margin-right</li>
        <li>margin-top</li>
        <li>max-block-size</li>
        <li>max-height</li>
        <li>max-inline-size</li>
        <li>max-width</li>
        <li>min-block-size</li>
        <li>min-height</li>
        <li>min-inline-size</li>
        <li>min-width</li>
        <li>object-fit</li>
        <li>object-position</li>
        <li>order</li>
        <li>overflow</li>
        <li>overflow-anchor</li>
        <li>overflow-block</li>
        <li>overflow-clip-margin</li>
        <li>overflow-inline</li>
        <li>overflow-wrap</li>
        <li>overflow-x</li>
        <li>overflow-y</li>
        <li>overscroll-behavior</li>
        <li>overscroll-behavior-block</li>
        <li>overscroll-behavior-inline</li>
        <li>overscroll-behavior-x</li>
        <li>overscroll-behavior-y</li>
        <li>padding</li>
        <li>padding-block</li>
        <li>padding-block-end</li>
        <li>padding-block-start</li>
        <li>padding-bottom</li>
        <li>padding-inline</li>
        <li>padding-inline-end</li>
        <li>padding-inline-start</li>
        <li>padding-left</li>
        <li>padding-right</li>
        <li>padding-top</li>
        <li>scroll-behavior</li>
        <li>scroll-margin</li>
        <li>scroll-margin-block</li>
        <li>scroll-margin-block-end</li>
        <li>scroll-margin-block-start</li>
        <li>scroll-margin-bottom</li>
        <li>scroll-margin-inline</li>
        <li>scroll-margin-inline-end</li>
        <li>scroll-margin-inline-start</li>
        <li>scroll-margin-left</li>
        <li>scroll-margin-right</li>
        <li>scroll-margin-top</li>
        <li>scroll-padding</li>
        <li>scroll-padding-block</li>
        <li>scroll-padding-block-end</li>
        <li>scroll-padding-block-start</li>
        <li>scroll-padding-bottom</li>
        <li>scroll-padding-inline</li>
        <li>scroll-padding-inline-end</li>
        <li>scroll-padding-inline-start</li>
        <li>scroll-padding-left</li>
        <li>scroll-padding-right</li>
        <li>scroll-padding-top</li>
        <li>scroll-snap-align</li>
        <li>scroll-snap-stop</li>
        <li>scroll-snap-type</li>
        <li>scroll-timeline</li>
        <li>scroll-timeline-axis</li>
        <li>scroll-timeline-name</li>
        <li>width</li>
    </ul>
</details>
<details>
    <summary><strong>Scope c-pos</strong></summary>
    <ul>
        <li>bottom</li>
        <li>left</li>
        <li>perspective</li>
        <li>perspective-origin</li>
        <li>position</li>
        <li>right</li>
        <li>top</li>
        <li>scale</li>
        <li>transform</li>
        <li>transform-box</li>
        <li>transform-origin</li>
        <li>transform-style</li>
        <li>translate</li>
        <li>z-index</li>
    </ul>
</details>
<details>
    <summary><strong>Scope c-txt</strong></summary>
    <ul>
        <li>column-count</li>
        <li>column-fill</li>
        <li>column-gap</li>
        <li>column-rule</li>
        <li>column-rule-color</li>
        <li>column-rule-style</li>
        <li>column-rule-width</li>
        <li>column-span</li>
        <li>column-width</li>
        <li>columns</li>
        <li>direction</li>
        <li>font</li>
        <li>font-family</li>
        <li>font-feature-settings</li>
        <li>font-kerning</li>
        <li>font-language-override</li>
        <li>font-optical-sizing</li>
        <li>font-palette</li>
        <li>font-size</li>
        <li>font-size-adjust</li>
        <li>font-stretch</li>
        <li>font-style</li>
        <li>font-synthesis</li>
        <li>font-variant</li>
        <li>font-variant-alternates</li>
        <li>font-variant-caps</li>
        <li>font-variant-east-asian</li>
        <li>font-variant-emoji</li>
        <li>font-variant-ligatures</li>
        <li>font-variant-numeric</li>
        <li>font-variant-position</li>
        <li>font-variation-settings</li>
        <li>font-weight</li>
        <li>hyphenate-character</li>
        <li>hyphenate-limit-chars</li>
        <li>hyphens</li>
        <li>letter-spacing</li>
        <li>line-break</li>
        <li>line-height</li>
        <li>text-align</li>
        <li>text-align-last</li>
        <li>text-combine-upright</li>
        <li>text-decoration</li>
        <li>text-decoration-color</li>
        <li>text-decoration-line</li>
        <li>text-decoration-skip</li>
        <li>text-decoration-skip-ink</li>
        <li>text-decoration-style</li>
        <li>text-decoration-thickness</li>
        <li>text-emphasis</li>
        <li>text-emphasis-color</li>
        <li>text-emphasis-position</li>
        <li>text-emphasis-style</li>
        <li>text-indent</li>
        <li>text-justify</li>
        <li>text-orientation</li>
        <li>text-overflow</li>
        <li>text-rendering</li>
        <li>text-shadow</li>
        <li>text-size-adjust</li>
        <li>text-transform</li>
        <li>text-underline-offset</li>
        <li>text-underline-position</li>
        <li>vertical-align</li>
        <li>white-space</li>
        <li>word-break</li>
        <li>word-spacing</li>
        <li>writing-mode</li>
        <li>-moz-osx-font-smoothing</li>
        <li>-webkit-font-smoothing</li>
    </ul>
</details>
<details>
    <summary><strong>Scope c-skin</strong></summary>
    <ul>
        <li>animation</li>
        <li>animation-delay</li>
        <li>animation-direction</li>
        <li>animation-duration</li>
        <li>animation-fill-mode</li>
        <li>animation-iteration-count</li>
        <li>animation-name</li>
        <li>animation-play-state</li>
        <li>animation-timing-function</li>
        <li>appearance</li>
        <li>backface-visibility</li>
        <li>background</li>
        <li>background-attachment</li>
        <li>background-clip</li>
        <li>background-color</li>
        <li>background-image</li>
        <li>background-origin</li>
        <li>background-position</li>
        <li>background-repeat</li>
        <li>background-size</li>
        <li>border</li>
        <li>border-bottom</li>
        <li>border-bottom-color</li>
        <li>border-bottom-left-radius</li>
        <li>border-bottom-right-radius</li>
        <li>border-bottom-style</li>
        <li>border-bottom-width</li>
        <li>border-collapse</li>
        <li>border-color</li>
        <li>border-image</li>
        <li>border-image-outset</li>
        <li>border-image-repeat</li>
        <li>border-image-slice</li>
        <li>border-image-source</li>
        <li>border-image-width</li>
        <li>border-left</li>
        <li>border-left-color</li>
        <li>border-left-style</li>
        <li>border-left-width</li>
        <li>border-radius</li>
        <li>border-right</li>
        <li>border-right-color</li>
        <li>border-right-style</li>
        <li>border-right-width</li>
        <li>border-spacing</li>
        <li>border-style</li>
        <li>border-top</li>
        <li>border-top-color</li>
        <li>border-top-left-radius</li>
        <li>border-top-right-radius</li>
        <li>border-top-style</li>
        <li>border-top-width</li>
        <li>border-width</li>
        <li>box-shadow</li>
        <li>caption-side</li>
        <li>color</li>
        <li>counter-increment</li>
        <li>counter-reset</li>
        <li>cursor</li>
        <li>filter</li>
        <li>list-style</li>
        <li>list-style-image</li>
        <li>list-style-position</li>
        <li>list-style-type</li>
        <li>mask</li>
        <li>mask-border</li>
        <li>mask-border-mode</li>
        <li>mask-border-outset</li>
        <li>mask-border-repeat</li>
        <li>mask-border-slice</li>
        <li>mask-border-source</li>
        <li>mask-border-width</li>
        <li>mask-clip</li>
        <li>mask-composite</li>
        <li>mask-image</li>
        <li>mask-mode</li>
        <li>mask-origin</li>
        <li>mask-position</li>
        <li>mask-repeat</li>
        <li>mask-size</li>
        <li>mask-type</li>
        <li>mix-blend-mode</li>
        <li>offset</li>
        <li>offset-anchor</li>
        <li>offset-distance</li>
        <li>offset-path</li>
        <li>offset-position</li>
        <li>offset-rotate</li>
        <li>opacity</li>
        <li>outline</li>
        <li>outline-color</li>
        <li>outline-offset</li>
        <li>outline-style</li>
        <li>outline-width</li>
        <li>page-break-after</li>
        <li>page-break-before</li>
        <li>page-break-inside</li>
        <li>pointer-events</li>
        <li>print-color-adjust</li>
        <li>quotes</li>
        <li>resize</li>
        <li>scrollbar-color</li>
        <li>scrollbar-gutter</li>
        <li>scrollbar-width</li>
        <li>shape-image-threshold</li>
        <li>shape-margin</li>
        <li>shape-outside</li>
        <li>tab-size</li>
        <li>touch-action</li>
        <li>transition</li>
        <li>transition-delay</li>
        <li>transition-duration</li>
        <li>transition-property</li>
        <li>transition-timing-function</li>
        <li>user-select</li>
        <li>-webkit-appearance</li>
    </ul>
</details>

### [CSS] Modifieur

Un modifieur `m-` est directement associé à un composant. Il n'a aucun effet s'il est utilisé seul. C'est une classe CSS qui vient ajouter ou surcharger une ou plusieurs propriétés CSS à son composant. Le modifieur peut affecter des [pseudo-classes](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-classes) et des [pseudo-éléments](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-elements). Le nom de cette classe est composé d'un préfixe `m-` et d'un nom, un abrégé qui désigne la ou les propriétés qu'il affecte (`ta-` pour text-align par ex.) et la valeur (`center` par ex.). Exemples :
* Le modifieur `m-main-space-between` associé à son composant `c-flex` applique la propriété `justify-content: space-between`. `m-main-space-between` appliqué seul n'a aucun effet.
  * `m-` : préfixe modifieur
  * `main-` : nom ou abstraction de la propriété affectée (ici l'axe main `justify-content` du composant flex)
  * `space-between` : valeur associée (`space-between`).
* Le modifieur `m-ta-center` associé à son composant `c-txt` applique la propriété `text-align: center`. `m-ta-center` appliqué seul n'a aucun effet.
  * `m-` : préfixe modifieur
  * `ta-` : nom ou abstraction de la propriété affectée
  * `center` : valeur associée (`center`).

### [CSS] Utilitaire

Un utilitaire `u-`est une classe qui affecte une et une seule propriété en la surchargeant (si elle est déjà définie) et en forçant son usage avec le mot-clé `!important`. L'utilitaire peut affecter des [pseudo-classes](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-classes) et des [pseudo-éléments](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-elements). Le nom de cette classe est composé d'un préfixe et d'un nom, souvent abrégé, qui désigne la fonctionnalité d'utilitaire. Exemples :
* L'utilitaire `u-bc-primary-500` applique et force la propriété `background-color` à la valeur associée à `primary-500`.
  * `u-` : préfixe utilitaire.
  * `bc-` : nom de la propriété affectée.
  * `primary-500` : nom de la valeur
  * `background-color: var(--ita-color-primary-500, #2C7DE5) !important` rendu CSS
* L'utilitaire `u-ta-center` applique et force la propriété `text-align` à la valeur associée à `center`.
  * `u-` : préfixe utilitaire.
  * `ta-` : nom de la propriété affectée.
  * `center` : nom de la valeur.
  * `text-align: center !important` rendu CSS

## [TOKENS] Design tokens

Les fondamentaux, également appelés *design tokens*, sont les parties élémentaires indivisibles du Design System à partir desquelles les composants, modifieurs et utilitaires sont créés.


```mermaid
classDiagram
    DesignTokens <|-- Colors
    DesignTokens <|-- ScreenSizes
    DesignTokens <|-- Fonts
    DesignTokens <|-- FontSizes
    DesignTokens <|-- Spacings
    DesignTokens <|-- BorderRadii
    DesignTokens <|-- Shadows
    Colors <|-- Color
    ScreenSizes <|-- ScreenSize
    Spacings <|-- Spacing
    Fonts <|-- Font
    FontSizes <|-- FontSize
    BorderRadii <|-- BorderRadius
    Shadows <|-- Shadow
    class DesignTokens{
        SASS Map
    }
    class Colors{
        SASS Map
    }
    class Color{
        CSS color
    }
    class ScreenSizes{
        SASS Map
    }
    class ScreenSize{
        Int
    }
    class Fonts{
        SASS Map
    }
    class Font{
        type
        path
        name
        filename
        fallback
    }
    class FontSizes{
        SASS Map
    }
    class FontSize{
        Int
    }
    class Spacings{
        SASS Map
    }
    class Spacing{
        Int
    }
    class BorderRadii{
        SASS Map
    }
    class BorderRadius{
        CSS border-radius
    }
    class Shadows{
        SASS Map
    }
    class Shadow{
        CSS box-shadow
    }
```

### [TOKENS] Couleurs

Le nombre de couleurs est illimité mais il doit respecter les règles suivantes&nbsp;: les couleurs s'organisent en familles, une famille de couleurs complète doit contenir 9 nuances de la plus sombre à la plus claire comme dans l'exemple ci-dessous. *Important&nbsp;: plus le nombre de familles de couleurs est élevé, plus les performances du framework sont impactées.*

La couleur principale de chaque famille est représentée par la **convention de désignation `<NOM_DE_LA_COULEUR>-500`**. Les valeurs abstraites `-400`, `-300`, `-200` et `-100` sont les nuances claires de la couleur principale et les valeurs `-600`, `-700`, `-800` et `-900` sont des nuances plus sombres.
Le nombre de couleurs est illimité mais il doit respecter les règles suivantes&nbsp;: les couleurs s'organisent en familles, une famille de couleurs complète doit contenir 9 nuances de la plus claire à la plus sombre comme dans l'exemple ci-dessous. *Important&nbsp;: plus le nombre de familles de couleurs est élevé, plus les performances du framework sont impactées.*

* `<NOM_DE_LA_COULEUR>-100` nuance la plus claire 
* `<NOM_DE_LA_COULEUR>-200` nuance claire 
* `<NOM_DE_LA_COULEUR>-300` nuance claire 
* `<NOM_DE_LA_COULEUR>-400` nuance claire 
* **`<NOM_DE_LA_COULEUR>-500` couleur principale**
* `<NOM_DE_LA_COULEUR>-600` nuance sombre
* `<NOM_DE_LA_COULEUR>-700` nuance sombre 
* `<NOM_DE_LA_COULEUR>-800` nuance sombre 
* `<NOM_DE_LA_COULEUR>-900` nuance la plus sombre 

Exemples de table de couleurs valide

https://tailwindcss.com/docs/customizing-colors

![image](https://user-images.githubusercontent.com/13103047/214549972-501c3dea-d4e4-4d90-bc92-dc8ec7026dc0.png)

https://getbootstrap.com/docs/4.0/getting-started/theming/#grays

![image](https://user-images.githubusercontent.com/13103047/214550347-0fa2b6db-33b9-472c-85c5-9d3c06797092.png)

Exemple de table de couleurs invalides
![Exemple de table de couleurs invalide](profile/css-colors-requirements-example-2-invalid.webp)


### [TOKENS] Espacements

Les espacements sont utilisés dans les marges, les positionnements ainsi que de nombreux composants, modifieurs et utilitaires. Le nombre d'espacements doit respecter une échelle d'incréments désignés comme suit. *Important&nbsp;: plus le nombre d'espacements est élevé, plus les performances du framework sont impactées.*

Les espacements sont classés par ordre croissant et nommés par une **convention de désignation sous forme d'index `<0 à n>` -> `<VALEUR>`**. 

* L'espacement `0` -> `0px` est réservé à l'équipe de développement front-end du ITADS, il n'est pas demandé au client. 
* `1` désigne l'espacement le plus petit fourni par le client.
* `n` désigne le plus grand espacement fourni par le client. 
* `n - 1` correspond à un espacement toujours plus petit que `n`.
* **`<VALEUR>`** chaîne de caractères définissant une longueur dans une unité CSS valide.

Exemple de table d'espacements valides, les différentes valeurs sont fournies par le client.

| Index / nom de l'espacement | Valeur |
|:-|:-|
| 14 | 112px |
| 13 | 96px |
| 12 | 80px |
| 11 | 64px |
| 10 | 56px |
| 9 | 48px |
| 8 | 40px |
| 7 | 32px |
| 6 | 24px |
| 5 | 20px |
| 4 | 16px |
| 3 | 12px |
| 2 | 8px |
| 1 | 4px |
| **0** <sup>1</sup> | **0px** <sup>1</sup> |

<sub>(1) L'espacement `0` -> `0px` est réservé à l'équipe de développement front-end du ITADS, il n'est pas demandé au client. <sub>

### [TOKENS] Polices de caractères

Une police de caractères est un ensemble de styles composé de 1 à 9 variations de graisses qui peuvent chacune être déclinées en italique. Une police de caractères peut donc regrouper 1 à 18 styles. 1 style = 1 graisse + italique oui ou non. Le nombre de polices de caractères est illimité, cependant *il est important de noter que plus le nombre de polices est élevé, plus les performances du framework sont impactées.* 

La convention d'appellation du design token pour une police de caractère est la suivante&nbsp;: **`<NOM_D_USAGE>-<GRAISSE>(-i)`**

* **Le `<NOM_D_USAGE>` est défini par l'équipe de développement, il doit être explicite par rapport à la fonction typographique qu'il occupe au sein du Design System.**
* **La `<GRAISSE>` de la police est définie sous forme de centaine comme dans le tableau de correspondance ci-dessous.**
* **-i est ajouté au design token si la police de caractère est italique**

Tableau d'équivalences nom des graisses / centaines CSS `font-weight`.

| Nom de la graisse | Équivalent en centaine CSS `font-weight` |
|:-|:-:|
| Thin | 100 |
| Extra-light | 200 |
| Light | 300 |
| Normal, ou regular | 400 |
| Medium | 500 |
| Semi-bold | 600 |
| Bold | 700 |
| Extra-bold | 800 |
| Black | 900 |

On différencie le nom d'usage du nom de la police afin d'éviter les écueils en cas de changement de police de caractères.

Par exemple `<NOM_D_USAGE>` est `lead` (personnalisation de l'équipe de développement) et `<NOM_DE_LA_POLICE>` est `Montserrat`. Si un jour la police lead doit être changée, sa fonction reste la même empêche la confusion au sein du Design System.

Par exemple pour une police dont le nom est "Montserrat Thin 100 Italic", on utilise un nom d'usage différent du nom de la police, par exemple "lead"

Exemple de design tokens de polices&nbsp;:

| Nom de la police | Nom d'usage | Graisse | Italique | Design token | Variable CSS |
|:-|:-|:-|:-|:-|:-|
| Montserrat | lead | Thin | non | `lead-100` | `--ita-font-family-lead-100` |
| Montserrat | lead | Light | non | `lead-300` | `--ita-font-family-lead-300` |
| Montserrat | lead | Regular | non | `lead-400` | `--ita-font-family-lead-400` |
| Montserrat | lead | Regular | oui | `lead-400-i` | `--ita-font-family-lead-400-i` |
| Montserrat | lead | Semi-bold | non | `lead-600` | `--ita-font-family-lead-600` |
| Montserrat | lead | Bold | non | `lead-700` | `--ita-font-family-lead-700` |
| Montserrat | lead | Black | non | `lead-900` | `--ita-font-family-lead-900` |
| Montserrat | lead | Black | oui | `lead-900-i` | `--ita-font-family-lead-900-i` |

Autre exemple de design tokens de polices&nbsp;:

| Nom de la police | Nom d'usage | Graisse | Italique | Design token | Variable CSS |
|:-|:-|:-|:-|:-|:-|
| Open Sans | lead | Regular | non | `lead-400` | `--ita-font-family-lead-400` |
| Open Sans | lead | Semi-bold | non | `lead-600` | `--ita-font-family-lead-600` |
| Open Sans | headline | Bold | non | `headline-700` | `--ita-font-family-headline-700` |
| Montserrat | headline | Black | non | `headline-900` | `--ita-font-family-headline-900` |
| Montserrat | headline | Black | oui | `headline-900-i` | `--ita-font-family-headline-900-i` |

### [TOKENS] Tailles de texte

Affectations de la taille des éléments textuels de type inline, principalement `font-size`. Le nombre de tailles de texte doit respecter une échelle d'incréments désignés comme suit. *Important&nbsp;: plus le nombre de tailles de texte est élevé, plus les performances du framework sont impactées.*

Les tailles de texte sont classés par ordre croissant et nommées par une **convention de désignation sous forme d'index `<1 à n>`**. 

* `1` désigne la taille de texte la plus petite fournie par le client.
* `n` désigne la plus grande tailler de texte fournie par le client. 
* `n - 1` correspond à une taille de texte toujours plus petite que `n`.

Exemple de tableau de correspondance de tailles de texte valides, les différentes valeurs sont fournies par le client.

| Index / nom de la taille de texte | Valeur | Variable CSS |
|:-|:-|:-|
| 15 | 60px | `--ita-font-size-15` |
| 14 | 54px | `--ita-font-size-14` |
| 13 | 48px | `--ita-font-size-13` |
| 12 | 42px | `--ita-font-size-12` |
| 11 | 36px | `--ita-font-size-11` |
| 10 | 32px | `--ita-font-size-10` |
| 9 | 28px | `--ita-font-size-9` |
| 8 | 24px | `--ita-font-size-8` |
| 7 | 20px | `--ita-font-size-7` |
| 6 | 18px | `--ita-font-size-6` |
| 5 | 16px | `--ita-font-size-5` |
| 4 | 14px | `--ita-font-size-4` |
| 3 | 12px | `--ita-font-size-3` |
| 2 | 10px | `--ita-font-size-2` |
| 1 | 8px | `--ita-font-size-1` |

### [TOKENS] Points de rupture

Également appelés "breakpoints" ou sous l'appellation "screen size", ils sont à la base du design adaptif ou "responsive". Les points de ruptures sont des design tokens, des noms personnalisés associés à des valeurs qui forment des intervalles entre lesquels les composants, modifieurs et utilitaires peuvent se comporter différemment. Ils sont directement liés à la taille du terminal de l'utilisateur. 

Le nombre de points de rupture n'est pas limité. *Cependant, plus le nombre de points de rupture est élevé, plus les performances du framework sont impactées.*

Les points de rupture sont nommés selon une **convention de désignation `<NOM_DU_POINT_DE_RUPTURE>` -> `<valeur>`**. 

Exemple de tableau de correspondance de points de rupture

| Nom du point de rupture | Intervalle affecté |
|:-|:-|
| xs | de 0 à 608 px |
| sm | de 608 px à 896 px |
| md | de 896 px à 1288 px |
| lg | de 1288 px à 1576 px |
| xl | de 1576 px à l'infini |

### [TOKENS] Coins arrondis

Un coin arrondi est défini par un ou deux rayons de courbure. Le nombre de coins arrondis n'est pas limité. *Cependant, plus le nombre de coins arrondis est élevé, plus les performances du framework sont impactées.* Les différentes valeurs/combinaisons de valeurs sont fournies par le client.

Les coins arrondis sont classés par ordre croissant et nommés par une **convention de désignation sous forme d'index `<0 à n>` -> `<VALEUR>`**. 

* Le coin arrondi `0` -> `0px` est réservé à l'équipe de développement front-end du ITADS, il n'est pas demandé au client. 
* `1` désigne le coin arrondi le plus petit fourni par le client.
* `n` désigne le plus grand coin arrondi fourni par le client. 
* `n - 1` correspond à un coin arrondi toujours plus petit que `n`.
* **`<VALEUR>`** chaîne de caractères directement liée à la valeur CSS comme décrite sur [cette page](https://developer.mozilla.org/fr/docs/Web/CSS/border-top-left-radius) et fournie par le client. Par exemple `10px`, `20%`, `15px 20%`.

Exemple de table coins arrondus valides, les différentes valeurs sont fournies par le client.

| Index / nom de l'arrondi | Valeur | Variable CSS |
|:-|:-|:-|
| 4 | 64px | `--ita-border-radius-4` |
| 3 | 32px | `--ita-border-radius-3` |
| 2 | 8px | `--ita-border-radius-2` |
| 1 | 4px | `--ita-border-radius-1` |
| **0** <sup>1</sup> | **0px** <sup>1</sup> | `--ita-border-radius-0` |

<sub>(1) Le coin arrondi `0` -> `0px` est réservé à l'équipe de développement front-end du ITADS, il n'est pas demandé au client. <sub>

### [TOKENS] Ombres portées ou Élévation

Également appelées **élévation**, les ombres portées sont de simples abstractions de la propriété CSS `box-shadow`. Le nombre d'ombres portées n'est pas limité. *Cependant, plus le nombre d'ombres portées est élevé, plus les performances du framework sont impactées.* Les valeurs des ombres portées sont fournies par le client.

Les ombres portées sont classées par ordre croissant d'élévation selon une **convention de désignation sous forme d'index `<0 à n>` -> `<VALEUR>`**. 

* L'élévation/ombre portée `0` -> `none` est réservé à l'équipe de développement front-end du ITADS, elle n'est pas demandée au client. 
* `1` désigne l'élévation/ombre portée la plus petite fournie par le client.
* `n` désigne la plus grande élévation/ombre portée fournie par le client. 
* `n - 1` correspond à une élévation/ombre portée toujours plus petite que `n`.
* **`<VALEUR>`** chaîne de caractères directement liée à la valeur CSS [box-shadow](https://developer.mozilla.org/fr/docs/Web/CSS/box-shadow) et fournie par le client. Les couleurs utilisées doivent être choisies parmi les design tokens de couleurs. Par exemple `10px 5px 5px 0px primary-100`.

| Index / nom de l'élévation | Valeur | Variable CSS |
|:-|:-|:-|
| 3 | 5px 3px 12px 0px neutral-100 | `--ita-shadow-3` |
| 2 | 2px 2px 8px 0px neutral-100 | `--ita-shadow-2` |
| 1 | 1px 1px 5px 0px neutral-100 | `--ita-shadow-1` |
| **0** <sup>1</sup> | **none** <sup>1</sup> | `--ita-shadow-0` |

<sub>(1) L'élevation nulle `0` -> `none` est réservée à l'équipe de développement front-end du ITADS, elle n'est pas demandée au client. <sub>

## [DEV] Variables CSS

Les design tokens sont disponibles sous forme de variables CSS désignées comme suit:

**`var(--ita-<TYPE_DE_TOKEN>-<NOM_DU_TOKEN>)`**

| Type de design token | Typologie variables CSS <TYPE> |
|:-|:-|
| `$briks-colors` | `var(--ita-color-<TOKEN_COULEUR>)` |
| `$briks-screen-sizes` | `var(--ita-screen-size-<TOKEN_TAILLE_ECRAN>)` | 
| `$briks-font-families` | `var(--ita-font-family-<token_fonte>)` |
| `$briks-font-sizes` | `var(--ita-font-size-<TOKEN_TAILLE_DE_FONTE>)` |
| `$briks-spacings` | `var(--ita-spacing-<TOKEN_ESPACEMENT>)` |
| `$briks-border-radius` | `var(--ita-border-radius-<TOKEN_ARRONDI>)` |
| `$briks-shadows` | `var(--ita-shadow-<TOKEN_ÉLÉVATION>)` |

Exemples de désignations 

```scss
$briks-colors: (
    primary-100: #061931,   // var(--ita-color-primary-100)
    primary-200: #0c3161,   // var(--ita-color-primary-200)
    primary-300: #124a92,   // var(--ita-color-primary-300)
    primary-400: #1863c2,   // var(--ita-color-primary-400)
    primary-500: #2C7DE5,   // var(--ita-color-primary-500)
    primary-600: #5697ea,   // var(--ita-color-primary-600)
    primary-700: #80b1ef,   // var(--ita-color-primary-700)
    primary-800: #abcbf5,   // var(--ita-color-primary-800)
    primary-900: #d5e5fa,   // var(--ita-color-primary-900)
$briks-screen-sizes: (
    xs: 0,                  // var(--ita-screen-size-xs)
    sm: 608,                // var(--ita-screen-size-sm)
    md: 896,                // var(--ita-screen-size-md)
    lg: 1080,               // var(--ita-screen-size-lg)
    xl: 1440                // var(--ita-screen-size-xl)
);
$briks-fonts: (
    lead-800: (             // var(--ita-font-family-lead-800)
        type:        'local',
        filename:    'subset-Sora-ExtraBold',
        name:        'Sora-ExtraBold',
        weight:      800,
        path:        '../fonts/Sora/',
        fallback:    'sans-serif'
    ),
    lead-400: (             // var(--ita-font-family-lead-400)
        type:        'local',
        filename:    'subset-Sora-Regular',
        name:        'Sora-Regular',
        weight:      400,
        path:        '../fonts/Sora/',
        fallback:    'sans-serif'
    )
);
$briks-font-sizes: (
    15: 60,                                 // var(--ita-font-size-15)
    14: 54,                                 // var(--ita-font-size-14)
    13: 48,                                 // var(--ita-font-size-13)
    12: 42,                                 // var(--ita-font-size-12)
    11: 36,                                 // var(--ita-font-size-11)
    10: 32,                                 // var(--ita-font-size-10)
    9: 28,                                  // var(--ita-font-size-9)
    8: 24,                                  // var(--ita-font-size-8)
    7: 20,                                  // var(--ita-font-size-7)
    6: 18,                                  // var(--ita-font-size-6)
    5: 16,                                  // var(--ita-font-size-5)
    4: 14,                                  // var(--ita-font-size-4)
    3: 12,                                  // var(--ita-font-size-3)
    2: 10,                                  // var(--ita-font-size-2)
    1: 8                                    // var(--ita-font-size-1)
);
$briks-spacings: (
    14: 112,                                // var(--ita-spacing-14)
    13: 96,                                 // var(--ita-spacing-13)
    12: 80,                                 // var(--ita-spacing-12)
    11: 64,                                 // var(--ita-spacing-11)
    10: 56,                                 // var(--ita-spacing-10)
    9: 48,                                  // var(--ita-spacing-9)
    8: 40,                                  // var(--ita-spacing-8)
    7: 32,                                  // var(--ita-spacing-7)
    6: 24,                                  // var(--ita-spacing-6)
    5: 20,                                  // var(--ita-spacing-5)
    4: 16,                                  // var(--ita-spacing-4)
    3: 12,                                  // var(--ita-spacing-3)
    2: 8,                                   // var(--ita-spacing-2)
    1: 4,                                   // var(--ita-spacing-1)
    0: 0,                                   // var(--ita-spacing-0)
);
$briks-border-radius: (
    0: 0,                                   // var(--ita-border-radius-0)
    1: 3,                                   // var(--ita-border-radius-1)
    2: 6,                                   // var(--ita-border-radius-2)
    3: 12,                                  // var(--ita-border-radius-3)
    4: 50,                                  // var(--ita-border-radius-4)
);
$briks-shadows: (
    0: none,                                    // var(--ita-shadow-0)
    1: 0px 0px 10px 0px my-color(neutral-100),  // var(--ita-shadow-1)
);
```


## [DEV] Conventions de désignations

La convention de désignation est la suivante: 

* **`<TYPE_D_OBJET>-<ABRÉGÉ_1>-<ABRÉGÉ_2>`** 
    * **`<TYPE_D_OBJET>`** peut être uniquement un modifieur `m-` ou un utilitaire `u-`.
    * **`<ABRÉGÉ_1>-`** abréviation de propriété CSS ou abstraction fonctionnelle.
    * **`<ABRÉGÉ_2>`** nom de la valeur, peut désigner directement la valeur (par ex. "center") ou une valeur abstraite comme un index.
* **Exemples d'abréviations de propriétés :**
    * `m-ta-center`
        * `ta-` désigne la propriété `text-align`.
        * `center` désigne la valeur.
* **Exemples d'abstractions fonctionnelles :**
    * `m-main-space-between` 
        * `m-` désigne qu'il s'agit d'un modifieur.
        * `main-` désigne l'axe "main" flexbox.
        * `space-between` désigne la valeur.
    * `m-fs-10` 
        * `m-` désigne qu'il s'agit d'un modifieur.
        * `fs-` désigne la propriété "font-size".
        * `10` désigne le design token numéro 10 sur lequel est assigné une taille de fonte.
    * `u-c-primary-500`
        * `u-` désigne qu'il s'agit d'un utilitaire.
        * `c-` désigne la propriété `color`.
        * `primary-500` désigne le design token couleur "primary-500" sur lequel est assignée une couleur.

## [DEV] Tableau des abréviations modifieurs

Abréviations désignant les propriétés CSS.

| Propriété CSS | Abréviation | Composant / modifieur associé | Utilitaire associé |
|:-|:-|:-|:-|
| animation | `anim-` | `c-skin m-anim-` | `u-anim-` |
| animation-delay | `animdel-` | `c-skin m-animdel-` | `u-animdel-` |
| animation-direction | `animdir-` | `c-skin m-animdir-` | `u-animdir-` |
| animation-duration | `animdur-` | `c-skin m-animdur-` | `u-animdur-` |
| animation-fill-mode | `animfm-` | `c-skin m-animfm-` | `u-animfm-` |
| animation-iteration-count | `animic-` | `c-skin m-animic-` | `u-animic-` |
| animation-name | `animn` | `c-skin m-animn` | `u-animn` |
| animation-play-state | `animps-` | `c-skin m-animps-` | `u-animps-` |
| animation-timing-function | `animtf-` | `c-skin m-animtf-` | `u-animtf-` |
| aspect-ratio | `ar-` | `c-dim m-ar-` | `u-ar-` |
| background | `bg-` | `c-skin m-bg-` | `u-bg-` |
| background-color | `bc-` | `c-skin m-bc-` | `u-bc-` |
| background-image | `bi-` | `c-skin m-bi-` | `u-bi-` |
| background-position | `bpos-` | `c-skin m-bpos-` | `u-bpos-` |
| background-repeat | `brep-` | `c-skin m-brep-` | `u-brep-` |
| background-size | `bsize-` | `c-skin m-bsize-` | `u-bsize-` |
| border | `b-` | `c-skin m-b-` | `u-b-` |
| border-style | `bstyle-` | `c-skin m-bstyle-` | `u-bstyle-` |
| border-top-style | `btstyle-` | `c-skin m-btstyle-` | `u-btstyle-` |
| border-right-style | `brstyle-` | `c-skin m-brstyle-` | `u-brstyle-` |
| border-bottom-style | `bbstyle-` | `c-skin m-bbstyle-` | `u-bbstyle-` |
| border-left-style | `blstyle-` | `c-skin m-blstyle-` | `u-blstyle-` |
| border-width | `bwidth-` | `c-skin m-bwidth-` | `u-bwidth-` |
| border-top-width | `btwidth-` | `c-skin m-btwidth-` | `u-btwidth-` |
| border-right-width | `brwidth-` | `c-skin m-brwidth-` | `u-brwidth-` |
| border-bottom-width | `bbwidth-` | `c-skin m-bbwidth-` | `u-bbwidth-` |
| border-left-width | `blwidth-` | `c-skin m-blwidth-` | `u-blwidth-` |
| border-color | `bcolor-` | `c-skin m-bcolor-` | `u-bcolor-` |
| border-image | `bimage-` | `c-skin m-bimage-` | `u-bimage-` |
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
| box-sizing | `bsizing-` | `c-dim m-bsizing-` | `u-bsizing-` |
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
| scroll-behavior | `scrollb-` | `c-dim m-scrolb-` | `u-scrollb-` |
| scroll-snap-align | `scrollsa-` | `c-dim m-scrollsa-` | `u-scrollsa-` |
| scroll-snap-type | `scrollst-` | `c-dim m-scrollst-` | `u-scrollst-` |
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

## [DEV] Helpers

Il existe des fonctions SASS dédiées à l'usage des design tokens. Elles retournent les variables CSS associées au design tokens accompagnées de leurs valeurs par défaut (au cas où la variable CSS n'existe pas).

### [DEV] my-color

```scss
my-color($token_couleur);
// Retourne
// var(--ita-color-TOKEN_COULEUR, <valeur_par_défaut>)
// Par exemple pour un token couleur primary-500: #123456
my-color(primary-500);
// Retourne
// var(--ita-color-primary-500, #123456)
```

### [DEV] my-font-family

```scss
my-font-family($token_fonte);
// Retourne
// var(--ita-font-family-token_fonte, <valeur_par_défaut>)
// Par exemple pour un token typo de nom lead-400
my-font-family(lead-400);
// Retourne
// var(--ita-font-family-lead-400, Sora-Regular, sans-serif)
```

### [DEV] my-font-size

```scss
my-font-size($token_taille_de_fonte);
// Retourne
// var(--ita-font-size-token_taille_de_fonte, <valeur_par_défaut>)
// Par exemple pour un token taille de fonte 9: 28
my-font-size(9);
// Retourne
// var(--ita-font-size-9, 28px)
```

### [DEV] my-spacing

Reprend le principe de raccourcis des propriétés CSS margin et padding.

#### [DEV] 4 côtés

```scss
my-spacing($token_espacement);
// Retourne
// var(--ita-spacing-token_espacement, <valeur_par_défaut>)
// Par exemple pour un token espacement 10: 56
my-spacing(10);
// Retourne
// var(--ita-spacing-10, 56px)
```

#### [DEV] vertical | horizontal

```scss
my-spacing($token_espacement_1, $token_espacement_2);
// Retourne
// var(--ita-spacing-token_espacement_1, <valeur_par_défaut_1>) var(--ita-spacing-token_espacement_2, <valeur_par_défaut_2>)
// Par exemple pour des tokens espacement 4: 16 et 3: 12
my-spacing(3, 4);
// Retourne
// var(--ita-spacing-3, 12px) var(--ita-spacing-4, 16px)
```

#### [DEV] haut | droit | bas | gauche

```scss
my-spacing($token_1, $token_2, $token_3, $token_4);
// Retourne
// var(--ita-spacing-token_1, <valeur_par_défaut_1>) var(--ita-spacing-token_2, <valeur_par_défaut_2>) var(--ita-spacing-token_3, <valeur_par_défaut_3>) var(--ita-spacing-token_4, <valeur_par_défaut_4>)
// Par exemple pour des tokens espacement:
// 3: 12,
// 4: 16,
// 5: 20,
// 6: 24,
my-spacing(3, 4, 6, 5);
// Retourne
// var(--ita-spacing-3, 12px) var(--ita-spacing-4, 16px) var(--ita-spacing-6, 24px) var(--ita-spacing-5, 20px)
```

### [DEV] my-border-radius

Reprend - en partie - le principe de raccourcis des propriétés CSS border-radius.

#### [DEV] global

```scss
my-border-radius($token_arrondi);
// Retourne
// var(--ita-border-radius-token_arrondi, <valeur_par_défaut>)
// Par exemple pour un token arrondi 2: 6
my-border-radius(2);
// Retourne
// var(--ita-border-radius-2, 6px)
```

#### [DEV] 2 arrondis

* **`$token_arrondi_1`** coin en haut à gauche et en bas à droite
* **`$token_arrondi_2`** coin en haut à droite et en bas à gauche

```scss
my-border-radius($token_arrondi_1, $token_arrondi_2);
// Retourne
// var(--ita-border-radius-token_arrondi_1, <valeur_par_défaut_1>) var(--ita-border-radius-token_arrondi_2, <valeur_par_défaut_2>)
// Par exemple pour des tokens arrondis 1: 3 et 2: 6
my-border-radius(1, 2);
// Retourne
// var(--ita-border-radius-1, 3px) var(--ita-border-radius-2, 6px)
```

#### [DEV] 4 arrondis

* **`$token_1`** coin en haut à gauche
* **`$token_2`** coin en haut à droite
* **`$token_3`** coin en bas à droite
* **`$token_4`** coin en bas à gauche

```scss
my-border-radius($token_1, $token_2, $token_3, $token_4);
// Retourne
// var(--ita-border-radius-token_1, <valeur_par_défaut_1>) var(--ita-border-radius-token_2, <valeur_par_défaut_2>) var(--ita-border-radius-token_3, <valeur_par_défaut_3>) var(--ita-border-radius-token_4, <valeur_par_défaut_4>)
// Par exemple pour des tokens arrondis:
// 0: 0,
// 1: 3,
// 2: 6,
// 3: 12,
my-border-radius(0, 3, 2, 1);
// Retourne
// var(--ita-border-radius-0, 0px) var(--ita-border-radius-3, 12px) var(--ita-border-radius-2, 6px) var(--ita-border-radius-1, 3px)
```

### [DEV] my-shadow

```scss
my-shadow($token_elevation);
// Retourne
// var(--ita-shadow-token_elevation, <valeur_par_défaut>)
// Par exemple pour un token élévation 1: 0px 0px 10px 0px my-color(neutral-100)
my-shadow(1);
// Retourne
// var(--ita-shadow-1, 0px 0px 10px 0px var(--ita-color-neutral-100, #000000))
```
