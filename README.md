# Air, a theme for [Hugo](https://gohugo.io/), a framework for building websites.

The intent of this theme is to provide a solid starting place for Hugo sites with basic features and include best practices for performance, accessibility, and rapid development.

## Screenshot

 ### Mobile
![screenshot](static/img/hugo-air-theme-mobile.jpg)
 
 ### Desktop
![screenshot](static/img/hugo-air-theme-desktop.jpg)

## Demo

[DEMO SITE](https://yeulocation.ducatillon.net/)

## Features

- Responsive
- Accessible
- Boostrap
- Customizable main color
- Responsive Embeded Google Maps
- Responsive Header Image from page bundle
- Image Gallery from page bundle available as **shortcode** or template page. (instagram or masonry style)
- Smooobu shortcode


## Installation

### As Git Submodule

Inside the folder of your Hugo site run:

```
$ git submodule add https://github.com/francoiducat/air.git themes/air
```

## Usage

### Edit your config file


```yml
baseURL: https://hugo-air-theme.com/
languageCode: fr-fr
title: Hugo Air Theme
theme: air
params:
  author:
    name: François
    siteUrl: https://notes.ducatillon.net/
  gmaps_url: https://www.google.com/maps/d/u/0/embed?mid=1UySq5HRbcRKL90dKuFpX6PRRtx0&ehbc=2E312F
  mainColor: "#386641"
  footer: "Hugo Air theme is great and customizable"
  scripts:
    bootstrap: |
      <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous" async></script>
    imageloaded: |
      <script src="https://cdnjs.cloudflare.com/ajax/libs/imagesloaded/4.1.4/imagesloaded.pkgd.min.js" async></script>
    masonry: |
     <script src="https://cdn.jsdelivr.net/npm/masonry-layout@4.2.2/dist/masonry.pkgd.min.js" integrity="sha384-GNFwBvfVxBkLMJpYMOABq3c+d3KnQxudP/mGPkzpZSTYykLBNsZEnG2D9G/X/+7D" crossorigin="anonymous" async></script>
    lightbox: |
      <script src="https://cdn.jsdelivr.net/npm/bs5-lightbox@1.8.3/dist/index.bundle.min.js" async></script>
menu:
  main:
  - name: Welcome
    url: /pages/welcome-page
    weight: 20
    params:
      target: 
```

### Customize main color

In your config file, add:

```yaml
params:
  mainColor: "#386641"
```

This will override the main.scss

```css
/*
=======================================================
=                   CSS Variables                     =
=======================================================
*/

/* 
Main color for the website
It can be overridden in the config file by setting "Params.mainColor" to any color value
*/
:root {
  --main-color: #035c8c; /* default color */
}
```

### Set Google Maps url

In your config file, add:

```yaml
params:
  gmaps_url: https://www.google.com/maps/d/u/0/embed?mid=1UySq5HRbcRKL90dKuFpX6PRRtx0&ehbc=2E312F
```

### Image Gallery

#### Use as partial
In your `.md` file, specify the type of the page with `type: gallery` like this:

```md
---
title: Air is a great hugo theme
type: gallery
---
Air is a great hugo theme with outstanding features like image gallery from page bundle
```

#### Use as shortcode

Assuming your folder structure would look something like this

```
content/
└── pages/
    └── my-page/                # Page Bundle
        ├── index.md            # Page content
        ├── featured-image.jpg  # Image Resource used as gallery image 1
        ├── photo1.jpg          # Image Resource used as gallery image 2
        ├── photo2.jpg          # Image Resource used as gallery image 3
        └── photo3.jpg          # Image Resource used as gallery image 4
````

In your `.md` file, include this block for a masonry gallery style:

```html
{{< gallery-masonry page="my-page">}}
```

where "my-page" is the page bundle object passed as a variable to the shortcode

Alternatively, use instagram gallery style with
```html
{{< gallery-insta page="my-page">}}
```


### Featured image

Add one image called `featured-image.jpg` in your page bundle.

#### Use as a featured header image in `single.html`
Automatically loaded as a header image on your page

##### Use the default featured header image
Automatically loaded from the `static/img` folder.
- `header-960.jpg` for screens higher than 960px
- `header-480.jpg` for screens lower than 960px

#### Use as featured card image in `list.html`
When listing pages, it displays boostrap cards with thumbnail image.