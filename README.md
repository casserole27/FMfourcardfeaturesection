# Frontend Mentor - Four card feature section solution

This is a solution to the [Four card feature section challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/four-card-feature-section-weK1eFYK). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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

## Overview

A "four card" design provided by Frontend Mentor.

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size

### Screenshot

![](/design/mymobile.png)
![](/design/mydesktop.png)

### Links

- Solution URL: [solution URL](https://www.frontendmentor.io/solutions/four-card-feature-section-using-responsive-css-grid-vZGriGOpU1)
- Live Site URL: [live site](https://www.clewisdev.com/FMfourcardfeaturesection/)

## My process

Setup basic HTML file 
- insert my personal comment credit
- <head> tag includes stylesheet/link and fonts, double check for meta viewport tag
- initial semantic, accessible markup: placing main, heading and paragraph tags
 - commit and push
Setup basic CSS file
- insert my personal comment credit
- copy style guide into file as comments
- decide on mobile or desktop-first design based on design file examples
- create *, root, and body selectors: margin/padding to 0, setup for variables, add font-family
- decide on which variables to use
- commit and push
Consult Figma design files
 - adjust text properties: size, line height, color
 - insert images and color properties
 - decide on layout tools and markup accordingly
 - add effects: borders, box shadows, etc
 - commit and push after each major change
Check markup and accessibility
(https://validator.w3.org/)
(https://wave.webaim.org/)
 - make adjustments as necessary
 - commit and push
 - live URL


### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

This was my first FrontEnd Mentor PRO project where I had access to the Figma design files. This is so much easier than trying to guess how everything looks! I have to admit I think that I did a good job copying the designs without these files, it's just more time consuming doing the guesswork. 
Since I had exact units for all the components of the design, I concentrated on precision.
I also took a lot of time to refine my knowledge of CSS grid and make responsiveness more seamless. 

Code that I'm proud of:
I did a small grid within the larger grid to achieve the individual layouts of the cards

```css
.supervisor-wrapper {
    grid-column: 2;
    grid-row: 2;
    display: grid;
    grid-template-columns: 1fr 75px;
    grid-template-rows: .5fr 1fr 1fr;
    border-radius: var(--br);
    border-top: solid .25rem var(--primary-cyan);
    box-shadow: 0px .25rem 2rem 0px rgba(0, 0, 0, 0.15);
}
```

I did not need that many lines of code to transition between the mobile and desktop designs. I'm very interested in a less clunky transition between screens and I think I am on my way to achieving this with this design. This below media query is all that was needed, and I placed an additional breakpoint of 1200px elsewhere in the cascade so that the design would look good on mobiles, tablets, and desktops. 

```css
@media screen and (min-width: 1080px) {

    :root {
        --fs-l: 2.25rem;
    }

    .grid-wrapper {
        column-gap: 2rem;
        row-gap: 1rem;
        grid-template-rows: repeat(4, 125px);
        justify-items: center;
    }

    .supervisor-wrapper {
        grid-column: 1;
        grid-row: 2 / 3;
        
    }

    .builder-wrapper {
        grid-row: 1;
    }

    .karma-wrapper {
        grid-row: 3 / 4;
    }

    .calculator-wrapper {
        grid-column: 3;
        grid-row: 2 / 3;
    }
}
```
### Continued development

With the precise measurements given by the Figma files, I am a bit confused about what sizing to use where. It seems that grid is really good at making sizing work for different viewports AUTOMATICALLY, but I simply could not figure out how to achieve the sizing provided in the design files without using specific pixels. I tried several different things such as sizing the grid, using min/max widths, and min(), max(), and clamp(). When trying to establish a minimum and maximum size, it never seems to get to the min size and always holds on to the max, even with minmax in the grid sizing.
Do you put the size on the grid, or the size on the grid elements? Is the specificity making it wonky? I have both going on and I don't know what is best practice or how to make this easier. I also have specific sizing on my main selector.
The design DOES work, but is there a better way?

```css
/******* GRID CONTAINER *******/

.grid-wrapper {
    /*! GRID DESIGN*/
    display: grid;
    grid-template-columns: minmax(2rem, 350px) minmax(311px, 350px) minmax(2rem, 350px);
    row-gap: 2rem;      
}

/****** GRID SIZING FOR CHILD ELEMENTS ******/

.supervisor-wrapper, .builder-wrapper, .karma-wrapper, .calculator-wrapper {
    display: block;
    width: 311px;
    height: 222px;
}


@media screen and (min-width: 1200px) {
    .supervisor-wrapper, .builder-wrapper, .karma-wrapper, .calculator-wrapper {
        width: 350px;
        height: 250px;
    }

}
```
```css
main { 
    background-color: white;
    min-width: 375px;
    max-width: 1440px;
    padding-bottom: 4.875rem;
}
```

Finally, after running markup and accessibility checkups, I made my own tweaks to the design. The provided colors did not give a proper contrast ratio for accessibility, so I changed these to darker blue/gray colors. I then made one of the headlines red for more visual interest. 

### Useful resources

Kevin Powell YouTube videos:
- [Learn CSS Grid the Easy Way](https://www.youtube.com/watch?v=rg7Fvvl3taU) 
- [Learn How to Create a Responsive CSS grid layout](https://www.youtube.com/watch?v=sKFW3wek21Q&list=PL4-IK0AVhVjPv5tfS82UF_iQgFp4Bl998&index=14) 
- [min(), max(), and clamp() are CSS magic!](https://www.youtube.com/watch?v=U9VF-4euyRo&list=PL4-IK0AVhVjODqX-gN6KH68Tt_zrYiTwA&index=3)


## Author

- Website - [C Lewis](https://www.clewisdev.com)
- Frontend Mentor - [@casserole27](https://www.frontendmentor.io/profile/casserole27)
- LinkedIn - [LinkedIn](https://www.linkedin.com/in/clewisdev/)


## Acknowledgments

[Kevin Powell's YouTube channel](https://www.youtube.com/kepowob)


