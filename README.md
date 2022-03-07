# Frontend Mentor - QR code component solution

This is a solution to the [QR code component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/qr-code-component-iux_sIO_H).

After getting burned out, I wanted to do something simple, so I took on this challenge. So, by completing this challenge at least I could get some motivation.

## Table of contents

- [Overview](#overview)
  - [Links](#links)
  - [Objective](#objective)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### Links

- Solution URL: []()
- Live Site URL: []()

### Objective
Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements
- See visible focus states for interactive elements when navigating by keyboard
- Understand and be able to navigate page content while using assistive technology

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- [Live Server - VS Code extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)

### What I learned

#### Multiple Approaches

So, I would like to share multiple ways that I can do to get the same result.

##### Simple and flat

This is the way that I took to finish this challenge. Nothing crazy is going on as far as the HTML markup and styling to create the card. Everything is straightforward, and I believe it is accessible.

```html
<main class="card">
  <img
    src="/images/image-qr-code.png"
    alt="Frontend Mentor QR Code"
    class="card__image"
    width="288"
    height="288"
  />
  <h1 class="card__title">
    Improve your front-end skills by building projects
  </h1>
  <p class="card__description">
    Scan the QR code to visit Frontend Mentor and take your coding
    skills to the next level
  </p>
</main>
```

This is the typical approach that most people would take.

##### It's a little more complicated, but it might be better?

This approach might be slightly complex.

```html
<main class="card">
  <h1 class="sr-only">
    QR code component example
  </h1>
  <div class="card__flex">
    <div class="card__text">
      <h2 class="card__title">
        Improve your front-end skills by building projects
      </h2>
      <p class="card__description">
        Scan the QR code to visit Frontend Mentor and take your coding
        skills to the next level
      </p>
    </div>
    <img
      src="/images/image-qr-code.png"
      alt="QR Code"
      class="card__image"
      width="288"
      height="288"
    />
  </div>
</main>
```

*Now, what is going on?* Well, let me explain it.
* Firstly, I add a visually hidden `h1` to give more structure and also clear that it is just an example or learning project. I could also think that this is just a chunk of the full website. So, the `h1` would exist somewhere else on the page.
* Second, I make the QR code image the second thing that screen reader users are read because, as far as I'm aware, text content is the king of content, and it would make sense if those users first listened to the text content to understand what the QR code is about.
* Lastly, I can simply use flexbox to change the appearance visually by using `flex-direction: column-reverse;`

##### Please, don't do this
This is the last approach that I could think of.

```html
<main class="card">
  <h1 class="card__title">
    Improve your front-end skills by building projects
  </h1>
  <p class="card__description">
    Scan the QR code to visit Frontend Mentor and take your coding
    skills to the next level
  </p>
</main>
```

*Where is the image?* The image is on the CSS. 😁

Well, this is the worst thing that I could think of. So, instead of putting an actual `img` element, I use either **pseudo-element** or `background` properties.

For normal users, I believe that it doesn't cause any problem because the image is still showing up. However, for the users of assistive technology, it causes a very serious issue where they don't know that there is a QR code image. The screen reader won't pronounce **pseudo-element** or any background images.

It's also more or less the same as the above approach.

```html
<main class="card">
  <img
    src="/images/image-qr-code.png"
    alt=""
    class="card__image"
    width="288"
    height="288"
  />
  <h1 class="card__title">
    Improve your front-end skills by building projects
  </h1>
  <p class="card__description">
    Scan the QR code to visit Frontend Mentor and take your coding
    skills to the next level
  </p>
</main>
```

> P.S. I could make it even worse by adding `aria-hidden="true"` to the image. That way, I make sure that not even a single screen reader would find out the image. 😂

### Useful resources
- [A Modern CSS Reset by Piccalilli](https://piccalil.li/blog/a-modern-css-reset/) - I usually use [Normalize](https://necolas.github.io/normalize.css/) which might be overkill for modern browsers since they are much likely to have fewer CSS browser compatibility issues.
- [The New CSS Reset | the-new-css-reset](https://elad2412.github.io/the-new-css-reset/) - This one is even newer and smaller which is great for modern browsers. I don't use it in this project, but it's a choice that exists.

## Author

- Frontend Mentor - [@vanzasetia](https://www.frontendmentor.io/profile/vanzasetia)
- Twitter - [@vanzasetia](https://www.twitter.com/vanzasetia)
