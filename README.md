# Frontend Mentor - Fylo landing page with two column layout solution

This is a solution to the [Fylo landing page with two column layout challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/fylo-landing-page-with-two-column-layout-5ca5ef041e82137ec91a50f5). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page

### Screenshot

![](screenshot.pdf)

### Links

- Solution URL: [Solution](https://github.com/JustANipple/fylo-landing-page-with-two-column-layout/blob/master/style.css)
- Live Site URL: [Live site](https://justanipple.github.io/fylo-landing-page-with-two-column-layout/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- Josh's Custom CSS Reset
- Active states transitions
- pseudo-classes
- Color picker

### What I learned

1. To make an email form that gives an error if you don't type an email, you need it to give it a pattern using regular expressions and give it the "required" rule so it doesn't send the form until you type a correct email
2. To show and to unshow an error message for the email form, don't use "display block", but instead visibility and opacity, so the element doesn't get out of the flow and you can give it a transition to make it look better
3. Use pseudo classes to make the email form change styling when on focus
4. If you have something like the "see how fylo works" block that gets a color change on hover, given the fact you can't change a color of an image just with "color: something", increase its brightness to make it like it switched colors
5. To make the fylo logo at the footer part white, just make it black filtering its brightness to 0 and then invert it so it gets white

This is the interesting part of the email form

HTML email form
```html
    <form action="#" class="header-email-form">
      <label for="typeEmail" hidden>Email:</label>
      <input 
      type="email" 
      id="typeEmail" 
      placeholder="Enter your email..."
      pattern="^[a-z0-9]+@[a-z0-9]+\.[a-z]+"
      required>
      <p class="error-message">
        Please check your email
      </p>
      <button type="submit" class="send-email">
        Get started
      </button>
    </form>
```

CSS email form
```css
#typeEmail:invalid:focus:not(:placeholder-shown) + .error-message {
  visibility: visible;
  opacity: 1;
  transition: visibility 0.5s ease, opacity 0.5s ease;
}

#typeEmail:invalid:focus:not(:placeholder-shown) {
  border: 1px solid red;
  outline-color: red;
}

#typeEmail:valid {
  border: 1px solid green;
  outline-color: green;
}

.error-message {
  visibility: hidden;
  opacity: 0;
  transition: visibility 0.5s ease, opacity 0.5s ease;
  color: red;
  text-align: left;
  font-size: 0.75rem;
  margin: 0.25rem 0;
}
```

### Continued development

I'd like to know more about pseudo classes. So far they i discovered nice features to make a site more responsive based on the user interactions

### Useful resources

- [Find a color](https://imagecolorpicker.com) - This color picker site helped me to find active states colors of interactive elements. At the end of this project i found a windows tool app that makes finding colors easier with PowerToys. I will use this next
- [Error message transition](https://stackoverflow.com/questions/3331353/transitions-on-the-css-display-property) - Here i discovered i shouldn't have used display block but instead the visibility and opacity rules to make the error message transitions

## Author

- Frontend Mentor - [@JustANipple](https://www.frontendmentor.io/profile/JustANipple)
