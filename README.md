<div align="center">

Shoelace Pug Loader
===

[![NPMCBT badge]][NPMCBT link]

*A Pug Mixin for easily loading Shoelace Web Components.*

</div>

[NPMCBT badge]: https://img.shields.io/npm/v/shoelace-pug-loader?color=CB3837&label=%20View%20on%20NPM&logo=npm&style=for-the-badge
[NPMCBT link]: https://www.npmjs.com/package/shoelace-pug-loader

## Getting Started

First, install with `npm i shoelace-pug-loader`.

Then, import the mixin into your Pug file:

```pug
include node_modules/shoelace-pug-loader/loader.pug

//- or from views/
include ../node_modules/shoelace-pug-loader/loader.pug
```

## Usage

### Selecting a theme

Shoelace has two themes: `light` and `dark`. You can load one or both of them by passing the theme name to the `slTheme` mixin:

```pug
+slTheme('dark')
```
#### Multiple themes

You may specify this twice to use both themes. See [Shoelace docs](https://shoelace.style/getting-started/themes?id=using-multiple-themes) for more info.

```pug
html
    head
        +slTheme('dark')
        +slTheme('light')
    body
        nav.sl-theme-dark
            h1 Dark-themed content
            p This is dark-themed content, enjoy it at night!
        h1 Light-themed content
        p The rest of the document is light-themed.
```

### Loading components

There are three ways to load components:

```pug
//- One at a time
+slComponent('button')
+slComponent('icon')

//- Multiple at once (note the plural form)
+slComponents('button', 'icon')

//- ALL components at once (this is NOT recommended)
+slAllComponents
```

### Using components

This mixin only **imports** the components. You still have to use them in your HTML.

```pug
html
    head
        +slTheme('dark')
        +slComponents('icon-button', 'tooltip')
    body
        sl-tooltip(content='Open settings')
            sl-icon-button(name='gear' label='Settings')
```

## License

**[ISC](LICENSE)**
