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
