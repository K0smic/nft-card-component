# Frontend Mentor - NFT preview card component solution

This is a solution to the [NFT preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/nft-preview-card-component-SbdUL_w0U). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Frontend Mentor - NFT preview card component solution](#frontend-mentor---nft-preview-card-component-solution)
  - [Table of contents](#table-of-contents)
  - [Overview](#overview)
    - [The challenge](#the-challenge)
    - [Screenshots](#screenshots)
  - [My process](#my-process)
    - [Built with](#built-with)
    - [What I learned](#what-i-learned)
    - [Useful resources](#useful-resources)
  - [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshots

<img src="/design/Final/Desktop.png" width="100%" height="auto"><img src="/design/Final/Mobile.png" width="100%" height="auto">

 ### Links

- Live Site URL: [Preview](https://k0smic.github.io/nft-preview-card-component/)

## My process

### Total time: 3h 45m

### Built with

- Semantic HTML5 markup
- CSS custom properties
- [npm](https://www.npmjs.com//)
- [Sass](https://sass-lang.com/)
- [Bootstrap 5](getbootstrap.com/) - npm + Bootstrap
- [Purgecss](https://purgecss.com/) - npm + Purgecss

### What I learned

This was the first time I followed any design instructions. I worked a few months as a full-stack developer using the "LAMP" stack, managing the whole project from scratch without any design guidelines.

First, I put my workspace back in place, re-installing everything I needed: "npm", "Sass", "Purgecss" and "Bootstrap".
I wasted some time at this stage.

Later I analyzed the design guidelines such as fonts, colors, sizes and images and I decided to use Bootstrap to make my life easier, especially the "Grid System" and the "Card" component. I imported everything into the Sass ".scss" file.

Once this was done, I started the actual project without any particular problem, following the images that were provided to me. The only difficulty came at the end with the overlay, and this is where I wasted a lot of time looking for some solution.

I put together something found on the internet using the "::after" selector and importing the icon directly into its content, but the issue is that the overlay worked but if you can the mouse went to the icon, the color was removed. Thinking back, I changed the method remembering other solutions, this time creating a second element after the image, with the same measures, after playing with "position: relative", "position: absolute" and "opacity" I was able to conclude.

Here is the final code of the overlay:

```html
<div class="card__image">
  <a href="#">
    <img src="images\image-equilibrium.jpg" class="card-img-top" alt="Equilibrium #3429" width="246px" height="246px" />
    <div class="card__image--hover">
      <img src="/images/icon-view.svg" alt="See more..." class="card__image--icon" />
    </div>
  </a>
</div>
```

```scss
.card {
  &__image {
    padding: 1.25rem;
    position: relative;
    .card-img-top,
    &--hover {
      height: 15.375rem;
      width: 15.375rem;
      max-height: 15.375rem;
      max-width: 15.375rem;
    }
    &--hover {
      opacity: 0;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      -ms-transform: translate(-50%, -50%);
      text-align: center;

      .card__image--icon {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        -ms-transform: translate(-50%, -50%);
      }
    }
    &--hover:hover {
      opacity: 0.7;
      background-color: hsl(178, 70%, 50%);
    }
  }
}
```

### Useful resources

- [Bootstrap v5.1 Docs](https://getbootstrap.com/docs/5.1/getting-started/introduction/) 

## Author

- Github - [K0smic](https://github.com/K0smic)
- Frontend Mentor - [@K0smic](https://www.frontendmentor.io/profile/K0smic)
