---
title: "Menú hamburguesa sólo con CSS (fácil)"
date: 2021-05-01T22:48:37-03:00
draft: false
categorías: ["HTML", "CSS"]
tags: ["principiante"]
---


¡Hola chicos! 
Una vez armada nuestra barra de navegación responsive, [ir al post](/2021/05/barra-de-navegacion-responsive-mobile-first/), vamos a ver como armar un menú hamburguesa **básico** sólo con CSS.

## HTML
Arranquemos con el código básico para el menú:
```html
<nav>
  <input type="checkbox" id="menu">
  <label for="menu"> Menu </label>
  <ul>
    <li>Link 1</li>
    <li>Link 2</li>
    <li>Link 3</li>
    <li>Link 4</li>
  </ul>
</nav>
```
### A tener en cuenta:
- Asignar un **id** al input. `<input type="checkbox" ` **`id="menu"`** `>` 
- Hacer referencia al **id** del input en el **for** del label. `  <label`**` for="menu"`**`> Menu </label>`

## CSS

Ahora con CSS, vamos a dar la funcionalidad a nuestro menú:

1. Ocultamos la lista de navegación `ul:{display: none;}`
2.  Ahora lo importante, con `input:checked  ~ ul` modificamos el estilo de la lista `ul` cuando el checkbox esté seleccionado (**checked**), por lo que allí es dónde modificamos el display de la lista, logrando que se visualice cuando el checkbox está marcado.

```css
ul{
  display: none;
}

input:checked  ~ ul{
  display:block;
}
```

Con ese simple código logramos lo siguiente:
![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/giiju7re812xtfajzgu2.gif)

## Dando estilo
Ahora lo que queda es dar estilo a nuestro menú hamburguesa:
- Ocultamos el input.
 ```css
 input {
  display: none;
}
```
- Modificamos el label y agregamos una imágen o icono de "hamburguesa".

```html
  <label for="menu"> ☰ </label>
```

```css
label {
  box-sizing: border-box;
  display: inline-block;
  border: 1px solid black;
  border-radius: 5px;
  width: 30px;
  height: 30px;
  line-height: 30px;
  font-weight: bold;
  text-align: center;
  user-select: none;
}
```
- Damos estilos a los elementos de la lista.
```css
li {
  display: block;
  background: lightgrey;
  margin: 0;
  padding: 10px;
  list-style: none;
  border-bottom: 1px solid grey;
}
```

Resultado final:
{{< codepen id="JjGVZPo" >}}
