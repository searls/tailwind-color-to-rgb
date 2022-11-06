# tailwind-color-to-rgb

Converts built-in [Tailwind](https://tailwindcss.com) color names to
space-separated RGB values for more easily referencing Tailwind's colors in [CSS
variables](https://tailwindcss.com/docs/customizing-colors#using-css-variables).

## Usage

Install it however you install npm packages. Globally that'd look like:

```
$ npm i -g tailwind-color-to-rgb
```

### As a CLI

This is a REPL module for converting Tailwind color names to space-separated RGB
values:

```
$ tailwind-color-to-rgb
Type a tailwind color for its space-separated RGB values

  Example:

  > rose-500
  244 63 94; /* rose-500 */

  Confused? See:
    https://tailwindcss.com/docs/customizing-colors#using-css-variables


> indigo-300
165 180 252; /* indigo-300 */
> white
255 255 255; /* white */
>
```

### As a JavaScript function

The package also exports a JavaScript function that will convert Tailwind's
color names to their space-separated RGB values:

```js
$ node
> const tailwindColorToRgb = require('tailwind-color-to-rgb')
undefined
> tailwindColorToRgb('yellow-500')
'234 179 8'
> tailwindColorToRgb('black')
'0 0 0'
```

## What is going on?

When specifying custom colors as CSS variables with Tailwind, the docs advise
you to define the variables as space-separated RGB values. This is necessary for
the framework to apply opacity modifiers. Here's the relevant [docs
page](https://tailwindcss.com/docs/customizing-colors#using-css-variables).

This package is just something I threw together to be able to quickly convert a
bunch of variables that I'd defined like this:

```css
  --inactive: theme('colors.gray.300');
```

With this package, I can just run the CLI and type:

```
> gray-300
```

And paste the resulting `209 213 219; /* gray-300 */` into my CSS file.

