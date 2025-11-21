# CSS Starter

A very basic, light-weight CSS to began with since browsers are pretty consistent when it comes to the basic styling nowadays.


### Box Sizing

By default css `width, height / inline-size, block-size` properties set the size of the content box not the size of whole box. So, when we add padding and border, those are all added on top of declared sizes.

`box-sizing: border-box` specifies that padding and borders should be included in the declared size.

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}
```

### Safari Auto Font Size Inflation

Prevent mobile browsers especially Safari from automatically adjusting font sizes in landscape mode, a feature in past meant to improve readability on non-optimized mobile sites.
Read more: https://kilianvalkhof.com/2022/css-html/your-css-reset-needs-text-size-adjust-probably/

```
html {
  -webkit-text-size-adjust: none; // Safari + older Chrome on Android. Safari only supports prefixed version.
  -moz-text-size-adjust: none; // Firefox mobile  needs the -moz- prefix
  text-size-adjust: none; // Standard property for modern browsers i.e. chromium
}
```

### Default Margin Adjustment

Remove default margin from specific elements. *(Add more elements as required and could also optionally set `padding: 0`.)*

```
body, h1, h2, h3, h4, p, figure, blockquote, dl, dd {
  margin: 0;
}
```

### Retain Sementic of Lists

Safari removes semantics of a list for Voice-over when `list-style: none` is applied. However, more recently Safari decided to preserve semantics of lists which are inside `<nav>`.

To maintain list semantics everywhere, add `role="list"` to lists.

```
[role='list'] {
  list-style: none;
  margin: 0;
  padding: 0;
}
```

### Set Line Height

```
body {
  min-block-size: 100vh;
  line-height: 1.6;
}

h1, h2, h3, button, input, label {
  line-height: 1.1;
}
```

### Better Text Wrapping

`text-wrap: balance` for better wrapping of headings. Usually developers nowadays add `text-wrap: pretty` in resets for paragraphs and lists to prevent orphan text but it's been omitted here for performance reasons.

> The necessary computations may be expensive, especially when applied to large amounts of text. Authors are encouraged to assess the impact on performance when using text-wrap-style: pretty, and possibly use it selectively where it matters most.

For performance reasons, text balancing only works when there is a limited number of lines and it stops working after the 5th / 6th line.

```
h1,
h2,
h3,
h4 {
  text-wrap: balance;
}
```

### Feedback & Contribute

Misses anything vital or have suggestions for improvements? Please open an issue or submit a PR.
