# Next.css Core Module

Core Module is part of [Next.css framework](https://github.com/nextcss). This module contains original Material Color Palette CSS styles for your Next.css project. You can use in all modern websites with module bundlers, like webpack, rollup, parcel.

**[Next.css on GitHub](https://github.com/nextcss)**

## How to Install

You can install with npm or yarn package managers.

```shell
npm i @nextcss/core @nextcss/reset @nextcss/material-colors
yarn add @nextcss/core @nextcss/reset @nextcss/material-colors
```

Simple import to your project, and add class rules to you HTML tags.
Check available selector rules below.

```javascript
import '@nextcss/reset';
import '@nextcss/core';
import '@nextcss/material-colors';
```

## How to use

Example feature list block. [Watch the resolution here](https://7q75l.csb.app/)
Learn more about available CSS selectors below.

```html
<section class="fs-16 lh-1.6 bg-grey-50 fg-grey-700 py-50">
  <!-- Container -->
  <div class="container-lg">
    <!-- Intro -->
    <div class="container-md text-center mb-20">
      <h1 class="fs-24 md:fs-30 fw-500 fg-grey-900 mb-10">Why Next.css</h1>
      <p>The world’s developers thinking in pixels, we also thinking in pixels.</p>
    </div>
    <!-- Feature list -->
    <div class="flex flex-wrap">
      <!-- Feature box -->
      <a href="#" class="md:w-12/6 lg:w-12/4 p-15">
        <div class="bg-white p-25 radius-3 shadow-1">
          <h2 class="fs-20 fw-500 fg-grey-900 mb-8">Shooting Stars</h2>
          <p class="leading-relaxed text-base mb-4">
            Fingerstache flexitarian street art 8-bit waistcoat. ...
          </p>
          <span class="fg-pink-500 inline-flex align-center">Learn More →</span>
        </div>
      </a>
      <!-- Repeated block here -->
      ...
    </div>
  </div>
</section>
```

## Table of Content

| Border                          | Floating        | Container               |
| ------------------------------- | --------------- | ----------------------- |
| [Border width](#border-width)   | [Float](#float) | [Container](#container) |
| [Border style](#border-style)   | [Clear](#clear) |                         |
| [Border radius](#border-radius) |                 |                         |

### Border width

```html
<!-- 3px border around -->
<div class="b-3">...</div>
```

**_around_**

- `b-[0...10]` (step: `1`, unit: `px`)
- `b-[15...100]` (step: `5`, unit: `px`)

**_x-axis, y-axis_**

- `b[x|y]-[0...10]` (step: `1`, unit: `px`)
- `b[x|y]-[15...100]` (step: `5`, unit: `px`)

**_top, right, bottom, left_**

- `b[t|r|b|l]-[0...10]` (step: `1`, unit: `px`)
- `b[t|r|b|l]-[15...100]` (step: `5`, unit: `px`)

### Border style

```html
<!-- 2px dashed border around -->
<div class="b-2 b-dashed">...</div>
```

**_common_**

- `b-[none|solid|dashed|dotted|double|groove|inset|outset|ridge]`

**_table_**

- `b-[collapse|separate]`

### Border radius

```html
<!-- 3px border radius -->
<div class="radius-3">...</div>
```

**_common_**

- `radius-[0...10]` (step: `1`)
- `radius-[15...100]` (step: `5`)
- `radius-[1000|10000]`

### Box sizing

```html
<!-- box-sizing: border-box -->
<div class="box-border">...</div>
```

**_common_**

- `box-[border|content]`

### Float

```html
<!-- Floating left side -->
<div class="float-left">...</div>
```

**_common_**

- `float-[left|right|none]`

### Clear

```html
<!-- Clear floating on left side -->
<div class="clear-left">...</div>
```

**_common_**

- `clear-[left|right|both|none]`

### Container

```html
<!-- Extra large container: 1280px -->
<div class="container-xl">...</div>
```

**_common_**

- `container-[xs|sm|md|lg|xl]`
- `xs` 480px `sm` 640px `md` 768px `lg` 1024px `xl` 1280px

## Production build

We strongly recommend to use `postcss` with `autoprefixer` and `postcss-purgecss`. This stack will extend the CSS rules with browser specific prefixes, like `-webkit` and will remove unused styles in production build.

```shell
npm i -D postcss autoprefixer @fullhuman/postcss-purgecss
```

Our `postcss.config.js` config. You need to configure the `content` parameter for your project.

```js
module.exports = {
  plugins:
    process.env.NODE_ENV === 'production'
      ? [
          'autoprefixer',
          [
            '@fullhuman/postcss-purgecss',
            {
              content: ['./{pages,components}/**/*.{js,jsx}'],
              safelist: ['html', 'body'],
              defaultExtractor: (content) => content.match(/[\w-/:]+(?<!:)/g) || [],
            },
          ],
        ]
      : ['autoprefixer'],
};
```

## License

MIT License. Copyright (c) 2021 Zsolt Tovis
