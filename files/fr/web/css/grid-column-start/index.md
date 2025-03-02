---
title: grid-column-start
slug: Web/CSS/grid-column-start
tags:
  - CSS
  - Propriété
  - Reference
translation_of: Web/CSS/grid-column-start
---

{{CSSRef}}

La propriété **`grid-column-start`** définit la position du début d'un élément (au sens des propriétés logiques `*-block-start`) en définissant la ligne ou la taille de fragment occupé sur la grille.

{{EmbedInteractiveExample("pages/css/grid-column-start.html")}}

## Syntaxe

```css
/* Valeur avec un mot-clé */
grid-column-start: auto;

/* Valeur <custom-ident> */
grid-column-start: unezonedegrille;

/* Valeurs <integer> + <custom-ident> */
grid-column-start: 2;
grid-column-start: unezonedegrille 4;

/* Valeurs span + <integer> + <custom-ident> */
grid-column-start: span 3;
grid-column-start: span unezonedegrille;
grid-column-start: span unezonedegrille 5;

/* Valeurs globales */
grid-column-start: inherit;
grid-column-start: initial;
grid-column-start: unset;
```

La valeur de cette propriété prend la forme d'une seule valeur `<grid-line>`. Une telle valeur peut être définie avec :

- le mot-clé `auto`
- ou une valeur `<custom-ident>`
- ou une valeur `<integer>`
- ou une valeur `<custom-ident>` et un `<integer>` séparés par un espace
- ou le mot-clé `span` avec une valeur `<custom-ident>` ou un `<integer>` ou les deux.

### Valeurs

- `auto`
  - : Un mot-clé qui indique que la propriété ne contribue pas au placement de l'élément sur la grille. Cela indique un placement automatique, une taille de fragment (_span_) automatique ou une taille par défaut de `1`.
- `<custom-ident>`

  - : S'il existe une ligne nommée avec '\<custom-ident>-start', la première ligne correspondante contribue au placement de l'élément sur la grille.

    > **Note :** Les noms des zones de grille sont générés implicitement. Ainsi, en utilisant `grid-column-start: foo;` cela sélectionnera le début de la grille nommée correspondante (sauf si une autre ligne `foo-start` a été explicitement déclarée).

    Sinon, la valeur est traitée comme si on avait utilisé `<custom-ident>` et la valeur `1`.

- `<integer> && <custom-ident>?`

  - : La n-ième ligne de la grille contribue au placement de l'élément sur la grille. Si un entier négatif est utilisé, le comptage sera fait depuis la fin de la grille explicite.

    Si un nom est fourni pour \<custom-ident>, seules les lignes ayant ce nom seront comptées. S'il n'y a pas suffisamment de lignes existant avec ce nom, toutes les lignes implicites seront comptées afin de trouver la position.

    Si la valeur entière utilisée est `0`, la règle est invalide.

- `span && [ <integer> || <custom-ident> ]`

  - : Un fragment de grille est utilisé pour le placement de l'élément sur la grille afin que le début de la ligne pour l'élément de la grille soit placé à n lignes du bord de fin.

    Si un nom fourni pour \<custom-ident>, seules les lignes ayant ce nom seront comptées. S'il n'y a pas suffisamment de lignes existantes avec ce nom, tout les lignes implicites du côté de la grille explicite et qui correspondent à la direction de la recherche seront comptées afin de placer ce fragment.

    Si l'entier n'est pas défini, la valeur par défaut qui sera utilisée sera `1`. Les entiers négatifs ou nuls sont invalides.

    ` <custom-ident``> ` ne peut pas prendre la valeur `span`.

## Définition formelle

{{CSSInfo}}

## Syntaxe formelle

{{CSSSyntax}}

## Exemples

```html
<div class="wrapper">
  <div class="box1">One</div>
  <div class="box2">Two</div>
  <div class="box3">Three</div>
  <div class="box4">Four</div>
  <div class="box5">Five</div>
</div>
```

```css
.wrapper {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 100px;
}

.box1 {
  grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 3;
}

.box2 {
  grid-column-start: 1;
  grid-row-start: 3;
  grid-row-end: 5;
}
```

```css hidden
* {box-sizing: border-box;}

.wrapper {
  border: 2px solid #f76707;
  border-radius: 5px;
  background-color: #fff4e6;
}

.wrapper > div {
  border: 2px solid #ffa94d;
  border-radius: 5px;
  background-color: #ffd8a8;
  padding: 1em;
  color: #d9480f;
}

.nested {
  border: 2px solid #ffec99;
  border-radius: 5px;
  background-color: #fff9db;
  padding: 1em;
}
```

{{EmbedLiveSample('Exemples', '230', '420')}}

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}

## Voir aussi

- {{cssxref("grid-column-end")}}
- {{cssxref("grid-column")}}
- {{cssxref("grid-row-start")}}
- {{cssxref("grid-row-end")}}
- {{cssxref("grid-row")}}
- [Guide : le placement sur les lignes d'une grille](/fr/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid)
- Tutoriel vidéo : [le placement sur les lignes (en anglais)](https://gridbyexample.com/video/series-line-based-placement/)
