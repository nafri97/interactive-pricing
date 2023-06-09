# Frontend Mentor - Interactive pricing component solution

This is a solution to the [Interactive pricing component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/interactive-pricing-component-t0m8PIyY8). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the app depending on their device's screen size
- See hover states for all interactive elements on the page
- Use the slider and toggle to see prices for different page view numbers

### Screenshot

![Desktop](./screenshot_Desktop.jpg)
![Mobile](./screenshot_Mobile.jpg)

### Links

- Solution URL: [Github Repository](https://github.com/nafri97/interactive-pricing)
- Live Site URL: [Github Page](https://nafri97.github.io/interactive-pricing)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Javascript
- [Vue.js](https://vuejs.org/) - JS Framework



### What I learned

So many I learned. Here's some sniplets:

```vue
   <span v-if="discount" class="price">{{ selectedText[2] }}</span>
   <span v-else class="price">{{ selectedText[1] }}</span>
```
watchEffect to change the value automatically when toggle clicked.
```vue
<script setup>
 import { ref, watchEffect } from 'vue'
    watchEffect(() => {
    if (discount.value) {
        showRed.value = true;
    } else {
        showRed.value = false;
    }
    });
</script>    
```
`event.target` is used to access the element that triggered the event, and `event.target.value` is used to get the current value of the input element.
```js
function onSliderChange(event) {
    const stepCount = parseInt(event.target.value);
}
```

### Continued development

I want to learn more vue.js because it has great documentation, and i want to strengthen my fundamental of Javascript as well.

### Useful resources

- [vue.js Reference](https://vuejs.org/guide/introduction.html) - This helped me to understand Vue.
- [W3schools-Javascript](https://www.w3schools.com/Javascript/) - This is an amazing article which helped me finally understand XYZ. I'd recommend it to anyone still learning this concept.
- [ChatGPT-OpenAI] (https://chat.openai.com/) - This is my reliable assistant.

## Author

- Github - [nafri97](https://www.github.com/nafri97)
- Frontend Mentor - [@nafri97](https://www.frontendmentor.io/profile/nafri97)
- Twitter - [@irfanrizkis](https://www.twitter.com/irfanrizkis)

## Acknowledgment
-
