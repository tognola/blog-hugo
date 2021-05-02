---
title: "Barra de navegación responsive (Mobile first)"
date: 2021-05-01T13:29:28-03:00
draft: false
author: "Gastón Tognola"
categorías: ["HTML", "CSS"]
tags: ["principiante"]
---
¡Hola chicos! Vamos a arrancar con un ejemplo de una barra de navegación responsive, usando Mobile First.

### Código básico de la barra de navegación: 
```html
<header>
  <h1> Titulo </h1>
  
  <nav>
    <span class="menu-button">☰</span>
    <ul>
      <li>Link 1</li>
      <li>Link 2</li>
      <li>Link 3</li>
      <li>Link 4</li>
    </ul>
  </nav>
  
</header>
```

### Puntos importantes en el estilo CSS:
- Contenedor header:
 - **display: flex** y **justify-content: space-between**. Para ubicar en extremos opuestos al logo y a la barra de navegación.

- Contenedor nav:
 - **ul: display: none**, ya que la idea es hacerlo mobile first, la lista de navegación se visualizará cuando se pase el mouse por arriba o se haga click en el botón del menú.

```css
*{
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
}

header{
  background-color: grey;
  height: 8vh;
  display: flex;
  justify-content: space-between;
}

header ul{
  display:none;
}

header h1{
  line-height: 8vh;
  margin-left:.5em;
}

.menu-button {
  display: inline-block;
  margin: 1vh;
  height: 6vh;
  width: 6vh;
  border: 1px solid black;
  line-height: 6vh;
  text-align: center;
}
```

### Vista de escritorio:
Dos cosas importantes a hacer ahora son:
- Ocultar el botón del menú (**.menu-button**) con **diplay:none**
- Ahora sí, visualizar la **lista*+ con los links de navegación con **display:block**.

Todo esto, por supuesto, dentro de un @media query.

```css 
@media screen and (min-width: 768px){
  .menu-button{
    display: none;
  }
  
  nav ul{
    display: block;
  }
  
  nav ul li{
    list-style: none;
    display: inline-block;
    line-height: 8vh;
    margin: 0 .5em;
  }
}
```

### Resultado

{{< codepen id="PoZgbQa" >}}

### Paso siguiente
Ahora queda dar funcionalidad al menú hamburguesa (sólo con css), [ver en este post](/2021/05/menu-hamburguesa-solo-con-css-facil/).