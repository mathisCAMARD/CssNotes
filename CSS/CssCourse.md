# **CSS SYNTHAX**

## Basic synthax :

- To write a comment :

```css
/*This is a comment*/
```

- To link an html file with a css file.Write in html header file (here style.css is the name of the css file):

```html
<link rel="stylesheet" href="style.css" />
```

---

## Text synthax :

- First of all, We have to choose the tag we want to implement. For instance if we want to modify the style of the title 1 of html file we have to write :

```css
h1 {
  /*Here we are going to write the style of all h1 from html file*/
}
```

- Exemple of text synthax :

```css
/* Import a synthax */
@import url("https://fonts.googleapis.com/css2?family=Grey+Qo&display=swap");

h1 {
  /* To put the letters in capital : */
  text-transform: uppercase;

  /* To change the space between the letters : */
  letter-spacing: 2px;

  /* To change the text size : */
  font-size: 2.5rem;

  /* To change the color of the text : */
  color: blueviolet;

  /* To create shadow (px:xy and blur) : */
  text-shadow: 5px 3px 0px blanchedalmond;

  /* To align text : */
  text-align: center; /* text-align: right ...*/

  /* To change the text stile :text-align : */
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;

  /* To import a new police : go to https://fonts.google.com an import before h1{}*/
  font-family: "Grey Qo", cursive;
}
```

---

## Backgroud

- Here some exemple to change the site background :

```css
body {
  font-family: "Times New Roman", Times, serif;

  /* To change te background color : */
  background-color: cadetblue;

  /* To add a backgroung image */
  background: url(./assets/pexels-pixabay-373290.jpg) fixed center/cover;
  height: 100vh;
}
```

---

## Box

- Here some exemple of text boxes :

```css
main {
  /* To change the color of the text box */
  background: cornsilk;

  /* To change the width of th text box */
  width: 90%; /*%of the screen user*/

  /* min-height: 500px; */

  /* To center the text and put a marge */
  margin: 10px 20px;
  margin-top: 10px;
  margin-left: 20px;
  margin: 0 auto; /*center*/

  /* To put a marge inside the text box */
  padding: 10px 20px;

  /* To change corner of the boxes : */
  border-radius: 10px;

  /* To put a shadow to the box : */
  box-shadow: 0 2px 12px 5px rgb(184, 24, 24);
}
```

---

## Positioning

- To supress all default configuration of padding and margin for title :

```css
* {
  margin: 0;
  padding: 0;
}
```

- To identify a title, div,... and change only this one :

```html
<div class="positioning">
  <h2>positioning</h2>
  <span>relative</span>
  <span id="circle">absolute</span>
  <span id="rectangle">egality</span>
</div>
```

```css
.positioning {
  /* Put border around the class positioning and modify it*/
  border: 2px solid skyblue;
  padding: 10px;
  margin-top: 20px;
  border-radius: 10px;
  position: relative;
}

#circle {
  /* Put border around the object circle declared in html */
  height: 60px;
  width: 60px;
  background: slateblue;
  padding: 20px;
  border-radius: 50%;
  /* The position of the oject is free in relativ of his parent */
  position: absolute;
  top: 50%;
  left: 50%;
  /* center the object */
  transform: translate(-50%, -50%);
}

#rectangle {
  height: 15px;
  width: 100px;
  background: springgreen;
  padding: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50px, -50px);
  /* To change what form is on top of the other */
  z-index: 1;
}
```

## ![image test](assets\Positioning.png "Positionning")

## Flexbox

- Used to align alement that have the same size
- flexbox generator : https://flexbox.help

```css
ul {
  /* Put elements of the parents on the same line */
  display: flex;

  /*  To equilify the place between the elements*/
  justify-content: space-around;
}
```

```css
li {
  list-style-type: none;
  font-size: 0.7rem;
  height: 160px;
  width: 160px;
  background: coral;

  /* Verticaly center */
  display: flex;
  align-items: center;
  justify-content: center;
}
```

## ![image test](assets\Flexbox.png "Flexbox")

## Grid

- Used to align and manage elements that have differents size

```html
<div class="grid">
  <h2>Grid</h2>
  <div class="grid-container">
    <img src="./assets/logo.png" height="200" alt="logo" />
    <form>
      <input type="text" id="firstname" placeholder="Firstname" />
      <input type="text" id="name" placeholder="Name" />
      <textarea
        name="textaerea"
        id=""
        cols="30"
        rows="10"
        placeholder="here your text"
      ></textarea>
      <input type="submit" value="valid" />
    </form>
  </div>
</div>
```

```css
form {
  display: grid;

  /* Create a grid */
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;

  /* We draw the design that we want for the frid */
  grid-template-areas:
    "i1 i2"
    "ta ta"
    "bt bt";
}
/* link the html parts with the name in grid template area */
#firstname {
  grid-area: i1;
}
#name {
  grid-area: i2;
}
textarea {
  grid-area: ta;

  /* user can't change the size of box */
  resize: none;
}
input[type="submit"] {
  grid-area: bt;

  /* change cursor on clikable part */
  cursor: pointer;

  /* change time of transition like for hover */
  transition: 0.4s;
}

/* Change element size when the pointer is on */
input[type="submit"]:hover {
  background: darkblue;
  color: white;
}
```

![image test](assets\Grid.png "Grid")

---

## Responsive

- Adapt the elements to the client page resizing

```css
/* Change elements comportements when page size under 1000px */
@media screen and (max-width: 1000px) {
  .grid-container {
    display: block;
  }
}

/* change grid placement when page size unde 700px */
@media screen and (max-width: 700px) {
  form {
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr 1fr 1fr;
    grid-template-areas:
      "i1"
      "i2"
      "ta"
      "bt";
  }
```

![image test](assets\Grid2.png "Grid resizing")
