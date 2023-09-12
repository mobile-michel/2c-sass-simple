---
title: 7-1 Pattern
description: Seven different folders and a single file at the root level
layout: base
stylesheet: main
tags: primary
---
## Base

The `base/` folder holds what we might call the boilerplate code for the project. In there, you might find some typographic rules, and probably a stylesheet (that I’m used to calling `_base.scss`), defining some standard styles for commonly used HTML elements.

## Components

For small components, there is the `components/` folder. While `layout/` is macro (defining the global wireframe), `components/` is more focused on widgets. It contains all kind of specific modules like a slider, a loader, a widget, and basically anything along those lines. There are usually a lot of files in components/ since the whole site/application should be mostly composed of tiny modules.

## Layout

The `layout/` folder contains everything that takes part in laying out the site or application. This folder could have stylesheets for the main parts of the site (header, footer, navigation, sidebar…), the grid system or even CSS styles for all the forms.

## Pages

If you have page-specific styles, it is better to put them in a `pages/` folder, in a file named after the page. For instance, it’s not uncommon to have very specific styles for the home page hence the need for a `_home.scss` file in `pages/`.

*Note — Depending on your deployment process, these files could be called on their own to avoid merging them with the others in the resulting stylesheet. It is really up to you.*

## Theme

On large sites and applications, it is not unusual to have different themes. There are certainly different ways of dealing with themes but I personally like having them all in a `themes/` folder.

*Note — This is very project-specific and is likely to be non-existent on many projects.*

## Abstracts

The `abstracts/` folder gathers all Sass tools and helpers used across the project. Every global variable, function, mixin and placeholder should be put in here.

The rule of thumb for this folder is that it should not output a single line of CSS when compiled on its own. These are nothing but Sass helpers.

## Vendors

Most projects will have a `vendors/` folder containing all the CSS files from external libraries and frameworks – Normalize, Bootstrap, jQueryUI, FancyCarouselSliderjQueryPowered, and so on. Putting those aside in the same folder is a good way to say “Hey, this is not from me, not my code, not my responsibility”.

If you have to override a section of any vendor, I recommend you have an 8th folder called `vendors-extensions/` in which you may have files named exactly after the vendors they overwrite. For instance, `vendors-extensions/_bootstrap.scss` is a file containing all CSS rules intended to re-declare some of Bootstrap’s default CSS. This is to avoid editing the vendor files themselves, which is generally not a good idea.

Reference: [Sass Guidelines](https://sass-guidelin.es/) > [Architecture](https://sass-guidelin.es/#architecture) > [Abstracts folder](https://sass-guidelin.es/#abstracts-folder)

### The 7-1 Patterned Structure
```
sass/
|
|- abstracts/
| |- _mixins // Sass Mixins Folder
| |- _variables.scss // Sass Variables
| |- _boilerplate.scss // Boilerplate Code
| |- _media-query.scss // 
| |- _colors.scss // 
|
|- core/
| |- _reset.scss // Reset
| |- _typography.scss // Typography Rules
|
|- components/
| |- _buttons.scss // Buttons
| |- _carousel.scss // Carousel
| |- _slider.scss // Slider
| |- _tabs.scss // Tabs
| |- _modals.scss // Modals
| |- _dropdown.scss // Modals
|
|- layout/
| |- _navigation.scss // Navigation
| |- _header.scss // Header
| |- _footer.scss // Footer
| |- _sidebar.scss // Sidebar
| |- _grid.scss // Grid
|
|- pages/
| |- _home.scss // Home styles
| |- _about.scss // About styles
| |- _contact.scss // Contact styles
|
|- sections/ (or blocks/)
| |- _hero.scss // Hero section
| |- _cta.scss // CTA section
|
|- vendors/ (if needed)
| |- _bootstrap.scss // Bootstrap
|
- app.scss // Main Sass file
```