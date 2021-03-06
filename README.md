# How I Made a Horizontal Carousel for My Responsive WebApp

![Apple Watch Pattern Library by Hanna Jung](https://miro.medium.com/max/480/1*UBAFXNsFeWLzbMt8Iky-Eg.gif)

Making the web accessible is a crucial feature to let the users experience it with satisfaction. The same precept applies when we display the information in our web app.

Horizontal scrollable fields became popular when mobile devices rose to stardom. Since then, there have been many cases where a carousel finds its perfect fit to showcase items.

Some of its advantages are:
- Horizontal scrollable fields are very intuitive with a well-designed UI.
- Swipe gestures allow users to move forth and backward through a subset of data.
- Keeps the website clean avoiding clunky column sets.

**Note:**

Find this tutorial in [GitHub](https://github.com/stiakov/carousel) and explore every step jumping over commits:

`git checkout <hash_number>`


## Laying out our carousel
_git checkout 9a5b614d39b3293132bca16e74d1a65cdb881f42_

Let’s add the basic components: One container and some divisions within.

```
/* index.html */

<body>
  <div id="carousel">
    <div class="item">🍎</div>
    <div class="item">🥑</div>
    <div class="item">🍋</div>
    <div class="item">🌽</div>
    <div class="item">🍇</div>
    <div class="item">🥭</div>
    <div class="item">🥝</div>
    <div class="item">🍑</div>
    <div class="item">🥦</div>
    <div class="item">🍓</div>
    <div class="item">🥕</div>
    <div class="item">🍅</div>
  </div>
</body>
```


## Making it horizontal with CSS rules
_git checkout 4d07f7c52eee4ce4e2596254f3b4af0adbc394d7_

Let’s add dimensions and borders to make it visible and flexbox to make it horizontal, do not forget to link your CSS file with the HTML.

```
/* index.html */

<head>
  <!-- ... -->
  <link rel="stylesheet" href="./styles.css">
</head>
<body>
  <!-- ... -->
</body>
```

```
/* styles.css */

#carousel {
  display: flex;
  
  margin: 0 auto 0 auto;
  width: 90vw;
  height: fit-content;
  
  border: dotted lightslategrey;
}

.item {
  min-width: 300px;
  min-height: 20vh;
  margin: 15px;

  font-size: 5em;
  text-align: center;
  line-height: 300px;
  border: solid orange 1px;
}
```


## Constrain the overflow over the X-axis
_git checkout bc22519554bafab063bfc0b595cfb8fc62eabde2_

Here is when the magic occurs, add and set the property overflow-x to auto and it will wrap all the divisions inside the container:

```
/* styles.css */

#carousel {
  /* ... */
  
  overflow-x: auto;
}
```

---

## Removing the scrollbar
_git checkout 99f877d20a58d8697e1cc7630de24abab63d40c5_

To hide the scrollbar we need to handle rules for the most popular [browser engines](https://en.wikipedia.org/wiki/Comparison_of_browser_engines).

```
/* styles.css */

#carousel {
  /* ... */
  -ms-overflow-style: none; /* Hide the scrollbar for MS EdgeHTML */
  scrollbar-width: none; /* Hide the scrollbar for Gecko based browsers as Mozilla Firefox */
}

#carousel::-webkit-scrollbar {
  display: none; /* Hide the scrollbar on Webkit based browsers as Chrome, Safari, etc */
}
```


## Final touches
_git checkout fdf7567a578d6bf7a684919c591a1fbf48ad2eb7_

Finally, let’s replace some and add an extra style to enhance the beauty of our carousel.

```
/* styles.css */

#carousel {
  /* ... */
  
  border: solid #F3E6FF .5px;
}
.item {
  /* ... */
  
  background-color: #FFF9EF;
  border-radius: 7px;
}
```


## Compendium

There you are, those are the completed code blocks.

```
/* index.html */

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="./styles.css">
  <title>Carousel V1</title>
</head>
<body>
  <div id="carousel">
    <div class="item">🍎</div>
    <div class="item">🥑</div>
    <div class="item">🍋</div>
    <div class="item">🌽</div>
    <div class="item">🍇</div>
    <div class="item">🥭</div>
    <div class="item">🥝</div>
    <div class="item">🍑</div>
    <div class="item">🥦</div>
    <div class="item">🍓</div>
    <div class="item">🥕</div>
    <div class="item">🍅</div>
  </div>
</body>
</html>
```

```
/* styles.css */

#carousel {
  display: flex;
  overflow-x: auto;
  -ms-overflow-style: none; /* Hide the scrollbar for MS Edge */
  scrollbar-width: none; /* Hide the scrollbar for Mozilla Firefox */

  margin: 0 auto 0 auto;
  width: 90vw;
  height: fit-content;
  
  border: solid #F3E6FF .5px;
}

#carousel::-webkit-scrollbar {
  display: none; /* Hide the scrollbar on Webkit based browsers (Chrome, Safari, etc) */
  -webkit-overflow-scrolling: touch; /* On touch screens the content continues to scroll for a while after finishing the scroll gesture */
}

.item {
  min-width: 300px;
  min-height: 20vh;
  margin: 15px;

  font-size: 5em;
  text-align: center;
  line-height: 300px;
  background-color: #FFF9EF;
  border-radius: 7px;
}
```

## Live Preview

- [GH-Pages](https://stiakov.github.io/carousel/)
- [CodePen](https://codepen.io/stiakov/pen/eYNpbyL)

## Author

👤 **Santiago Torres G.**

* [GitHub](https://github.com/stiakov)
* [LinkedIn](https://www.linkedin.com/in/stiakov/)
* [Twitter](https://twitter.com/st_iakov)
