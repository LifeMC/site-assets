# site-assets
Public site assets for the LifeMC site.

# img
Contains the images. Preference order: AVIF > WebP > JPG > PNG.

The PNG can be more qualitive but for speed, AVIF is best.

# css
Contains the styles. All of them should be minimized.

If there are third party styles there, that means we've edited them
to increase performance.

# fonts
Contains the fonts. Can contain all font types, but WOFF 2.0 is preferred.

All of them should be loaded with font-display: swap to increase performance.

# js
Contains the javascript files. Should be seperated as head and body, where head is important ones and body unimportant.
If it is not either head or body, it is a special case which is sent by web server conditionally.

i.e snow on only month of December. It can be checked inside JS too, but avoiding a network request entirely when
not in December is more performance friendly.

All of them should be starting with "use strict"; to use strict mode.

# usage
Bootstrap 3:

You need to add cdn.statically.io to your script-src-elem or script-src directives if you're using a content security policy (CSP) on your site.

```html
<link rel="font preload" href="https://cdn.statically.io/gh/LifeMC/site-assets/main/fonts/bootstrap/3.4.1/glyphicons-halflings-regular.woff2" as="font" crossorigin="anonymous">
<link rel="stylesheet preload" href="https://cdn.statically.io/gh/LifeMC/site-assets/main/css/bootstrap/3.4.1/bootstrap.min.css" as="style">
```

FontAwesome 4:

You need to add cdn.statically.io to your script-src-elem or script-src directives if you're using a content security policy (CSP) on your site.

```html
<link rel="font preload" href="https://cdn.statically.io/gh/LifeMC/site-assets/main/fonts/font-awesome/4.7.0/fontawesome-webfont.woff2" as="font" crossorigin="anonymous">
<link rel="stylesheet preload" href="https://cdn.statically.io/gh/LifeMC/site-assets/main/css/font-awesome/4.7.0/font-awesome.min.css" as="style">
```

DeferJs:

You need to add cdn.statically.io to your script-src-elem or script-src directives if you're using a content security policy (CSP) on your site.

```html
<script src="https://cdn.statically.io/gh/LifeMC/site-assets/main/js/main/v1/defer.min.js"></script>
```

And then you can use <script defer async type="deferjs"></script> tags. Inline scripts and scripts from sources (the src attribute) are supported.
To learn more about DeferJs, see https://github.com/shinsenter/defer.js/commits/master

Note: This not receive updates from the repository anymore and is not used by LifeMC main site anymore, therefore not supported.

Snowstorm:

You need to add cdnjs.cloudflare.com and cdn.statically.io to your script-src-elem or script-src directives if you're using a content security policy (CSP) on your site.

With PHP only on month of December:

```php
<?php if (date('n') === '12') { echo '<script defer src="https://cdnjs.cloudflare.com/ajax/libs/Snowstorm/20131208/snowstorm-min.js"></script><script defer src="https://cdn.statically.io/gh/LifeMC/site-assets/main/js/main/v1/snow.min.js"></script>'; }?>
```

With HTML always:

```html
<script defer src="https://cdnjs.cloudflare.com/ajax/libs/Snowstorm/20131208/snowstorm-min.js"></script>
<script defer src="https://cdn.statically.io/gh/LifeMC/site-assets/main/js/main/v1/snow.min.js"></script>
```

# notes
Although some of our base libraries (Bootstrap, FontAwesome, etc.) are behind the latest major versions, they don't contain any security vulnerabilities and
we have edited them for our performance needs, to make PageSpeed Insights not complain about font-display swap, for example.

We will update our base library eventually though, but we'll avoid the hassle of upgrading until we think it is certainly needed.
