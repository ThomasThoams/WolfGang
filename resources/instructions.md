# Module 6 - WOLF GANG

- [Module 6 - WOLF GANG](#module-6---wolf-gang)
  - [Nouveautés dans ce module](#nouveautés-dans-ce-module)
    - [Côté HTML](#côté-html)
    - [Côté CSS](#côté-css)
    - [Côté accessibilité](#côté-accessibilité)
      - [L'attribut aria-label](#lattribut-aria-label)
      - [Introduction à aria-live : prévenir le lecteur d’écran d’un changement.](#introduction-à-aria-live--prévenir-le-lecteur-décran-dun-changement)
  - [Utiliser un CDN : polices d'icones BOOSTRAP](#utiliser-un-cdn--polices-dicones-boostrap)
  - [CSS et charte graphique](#css-et-charte-graphique)
  - [Diaporama](#diaporama)
    - [Insertion du javascript fourni pour faire fonctionner le diaporama (slider)](#insertion-du-javascript-fourni-pour-faire-fonctionner-le-diaporama-slider)
    - [Code HTML](#code-html)
      - [Classes d'éléments obligatoire](#classes-déléments-obligatoire)
      - [Les éléments HTML](#les-éléments-html)
      - [CSS](#css)

## Nouveautés dans ce module 

### Côté HTML 

1. La balise `<figure>` : https://www.alsacreations.com/article/lire/1337-html5-elements-figure-et-figcaption.html
2. Insérer du code javascript dans une page HTML : https://developer.mozilla.org/fr/docs/Web/HTML/Element/script
3. L'attribut `rel` : https://developer.mozilla.org/fr/docs/Web/HTML/Attributes/rel
4. Le format SVG : https://www.alsacreations.com/tuto/lire/1421-svg-initiation-syntaxe-outils.html
5. Insertion de vidéo : 
   1. https://www.alsacreations.com/article/lire/1125-introduction-balise-video-html5-mp4-h264-webm-ogg-theora.html
   2. https://developer.mozilla.org/fr/docs/Web/HTML/Element/video
   3. https://caniuse.com/?search=video (Voir les compatibilités en fonction des différents formats)

### Côté CSS

1. Adopter la flexitude
2. La propriété `box-sizing` : https://developer.mozilla.org/fr/docs/Web/CSS/box-sizing
3. Dégradés CSS avec la propriété `background` : https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Images/Using_CSS_gradients3. 
4. La transparence de couleur : https://www.alsacreations.com/tuto/lire/909-CSS-transparence-couleur-rgba.html
5. Effet d'ombrage :
   1. Sur les boites (`box-shadow`) : https://developer.mozilla.org/fr/docs/Web/CSS/box-shadow
   2. Sur le texte (`text-shadow`): https://developer.mozilla.org/fr/docs/Web/CSS/text-shadow
6. Positions CSS (à suivre pendant le cours)

### Côté accessibilité 

#### L'attribut aria-label 

L'attribut aria-label est utilisé pour définir une légende non-visible associée à un élément HTML dont le sens est transmis uniquement par le visuel. Par exemple, une flèche pour charger la ressource suivante.

#### Introduction à aria-live : prévenir le lecteur d’écran d’un changement.

Les zones « live » ARIA fournissent des solutions aux lecteurs d’écran afin de savoir si et comment interrompre l'utilisateur lors d’un changement.

[Zones live ARIA](https://developer.mozilla.org/fr/docs/Web/Accessibility/ARIA/ARIA_Live_Regions)

Voir aussi :
[L’ATTRIBUT TITLE : À CONSOMMER AVEC MODÉRATION](https://www.24joursdeweb.fr/2013/attribut-title-avec-moderation/)

## Utiliser un CDN : polices d'icones BOOSTRAP 

Le terme « réseau de distribution de contenu » (Content Delivery Network, CDN) désigne un groupe de serveurs géographiquement distribués travaillant de concert afin de diffuser rapidement un contenu Internet.

Installer la police d'icônes proposée par BOOTSTRAP via leur CDN : https://icons.getbootstrap.com/#install

## CSS et charte graphique 

* Démarche mobile-first - 2 points de rupture : 768px, 1024px
* Jeux de polices par défaut : Arial, Helvetica, sans-serif;
* Police utilisée pour les titres et la navigation : "Bodega Sans" : le fichier de police est fourni (déclaration locale)
* Couleur du texte par défaut : white
* Couleur du texte secondaire (sur fond blanc) : #666
* Couleur de relief (orange): #ff9d00 ( Valeur RGB : rgb(255, 157, 0) )
* Couleur de fond : #444 + image de fond
* Taille des titres (à exprimer en unite proportionnelle):
  * Niveau 1 : 40px par défaut (soit 4rem)
  * Niveau 2 : 30px par défaut
  * Niveau 3, lien de la navigation principale : 25px par défaut
* Hauteur de ligne : 2 fois la hauteur d'un caractère 
* Taille maximale : 1500px

## Diaporama

Les photos présentes dans le dossier img/slider sont prévues pour s'afficher sous forme de diaporama.
Au chargement, seule la première photo ne doit apparâitre
Lorque l'utilisateur clique sur un élément déclencheur, l'élément affiché doit disparaitre et l'élément suivant ou précédent doit apparaître.

### Insertion du javascript fourni pour faire fonctionner le diaporama (slider)

Intégrer le code javascript fourni dans le fichier : `js/slider.js`

Quel est le meilleur emplacement de déclaration, sachant que :

1. les scripts (sans attribut async ou defer) sont chargés et exécutés immédiatement avant que le navigateur continue l'analyse de la page.
2. le code javascript fourni cible des balises du DOM
3. le code ne s'exécute qu'après action de l'utilisateur  

#### Remarques :

1. La balise "script" n'est pas auto-fermante, c'est-à-dire que l'on ne peut pas écrire `<script type="text/javascript" ... />`
2. L'attribut type doit être renseigné avec la syntaxe XHTML, mais il peut être omis en HTML5.

Voir aussi : https://www.alsacreations.com/astuce/lire/80-Comment-integrer-du-code-JavaScript-dans-une-page-.html

### Code HTML 

#### Classes d'éléments obligatoire

Le javascript cible des classes d'élément; pour fonctionner, le code HTML suivant doit être présent dans la page : 

1. Tous les composants du slider doivent se trouver dans un conteneur : `class="slider"`
2. Les éléments qui défilent doivent avoir un attribut classe imposé : `class="slider-figure"` 
3. L'élément affiché doit également avoir une deuxième classe, présente au chargement de la page  : `class="slider-figure is-active"`
4. Les éléments déclencheurs sont au nombre de 2 :
   1. Pour reculer : `class="slider-nav-link prev"`
   2. Pour avancer : `class="slider-nav-link next"`

Lorsque le code HTML sera prêt, le journal de la console du navigateur affichera "Le slider est prêt à fonctionner"

#### Les éléments HTML

1. Le conteneur global du composant slider (`class="slider"`) doit rester indépendant, on privilégiera un balisage neutre.
2. Les photos du diaporama seront légendées, sans provoquer de répétition vocale avec l'attribut `alt des photos`.
3. Les éléments déclencheurs doivent chargés une nouvelle ressource, ils constituent donc une navigation, et sont généralement réprésentés par des flèches : 
   1. L'occasion d'exploiter l'attribut `rel` sur des liens (https://developer.mozilla.org/fr/docs/Web/HTML/Attributes/rel)
   2. et de rendre accessible l'intitulé des liens (Photo suivante, photo précédente) avec `aria-label` 

Bonus : Rajouter l'attribut `aria-live` sur le conteneur 


#### CSS

Les comportements CSS sont à votre charge : 

1. N'afficher que la première figure au chargement
2. Positionner la légende ainsi que les flèches de défilement sur les photos  

Nota : Ils sont généralement fournis avec une feuille de styles associés au script, mais cela ne serait pas drôle !