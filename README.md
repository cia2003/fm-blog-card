# Frontend Mentor - Blog preview card solution

This is a solution to the [Blog preview card challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/blog-preview-card-ckPaj01IcS). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- See hover and focus states for all interactive elements on the page

### Screenshot

on desktop screen:

![](/screenshots/desktop-ss.png)

on mobile screen:

![](/screenshots/mobile-ss.png)

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox

### What I learned
For the first time, I learn to use @font-face to add customize font. Usually, I use embedded code at the head of html to add new font family. 

```html
<head>
  <!-- Other code -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Courier+Prime:ital,wght@0,400;0,700;1,400;1,700&family=Figtree:ital,wght@0,300..900;1,300..900&family=Outfit:wght@100..900&family=Quicksand:wght@300..700&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
</head>
```

Right now, I start to use @font-face and I think it really helpful when there is not online access to google font. So, I can still display the new font family without access it online.

```css
@font-face {
    font-family: 'Figtree';
    src: url('../assets/fonts/Figtree-VariableFont_wght.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
}
```

As I dive into CSS, I realized that I need to make the font size relative to the screen. Usually, I make a fixed size font, like this example below:

```css
main .content #card-blog .card-content .card-title {
    font-size: 24px;
    line-height: 150%;
    letter-spacing: 0px;
    margin: 0;
}
```
But then, It will give a problem on the smaller screen 

![](/screenshots/title-breakword.png)

How to make the font responsive? I see that 'vw' can be used to make it responsive, but the problem is that the font will be too wide in larger screen or too small in smaller screen. How to prevent that? I used clamp to give its maximum and minimum value for the font-size.

```css
main .content #card-blog .card-content .card-title {
  /* Other codes */
    font-size: clamp(1.2rem, 5vw, 1.5rem);
}
```
I only take a guess for the preferred value so it can be suitable for medium screen size.

### Continued development

I want to deepened my knowledge of how to calculate the preferred value as a medium value within the range. I think it will helpful because the middle value will be suit for medium screen.

### Useful resources

- [Relative length units based on font](https://developer.mozilla.org/en-US/docs/Web/CSS/length#relative_length_units_based_on_font) - This helped me to understand the difference usage of relative units.
- [Clamp](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp) - This helped me to understand about range value.

## Author

- Frontend Mentor - [@cia2003](https://www.frontendmentor.io/profile/cia2003)
#