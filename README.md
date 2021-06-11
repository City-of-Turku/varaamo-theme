# varaamo-theme
An example of a varaamo theme.
## Installation
Currently the only way of actually using a theme is to install it locally.

1. Place the `varaamo-theme` folder next to the `varaamo` folder
  * Like this:
    ```
    /varaamo
    /varaamo-theme
    ```
2. In the `varaamo` project folder run `npm install ../varaamo-theme`


## Development
Install the theme according to the installation instructions and then `npm link`
the local theme to the local varaamo project.

```
cd ~/projects/varaamo-theme
npm link
cd ~/projects/varaamo
npm link varaamo-theme
```


## Configuration

### constants
The index files contents override values in the varaamo `AppConstants.js` file.
Currently the only values that can be overridden are:
* FEEDBACK_URL
* NAV_ADMIN_URLS
* MAP_TILE_URLS

#### FEEDBACK_URL
Contains language specific key/values for the feedback url that is shown in the footer.
```
FI: 'https://url-to-finnish-feedback.com,
SV: 'https://url-to-swedish-feedback.com,
EN: 'https://url-to-english-feedback.com
```

#### NAV_ADMIN_URLS
Contains the urls to the admin guide that appears in the navbar for admins.
```
gitbook: 'https://url-to-finnish-or-default-admin-guide.com,
gitbook_sv: 'https://url-to-the-swedish-admin-guide.com,
```

#### MAP_TILE_URLS
Contains the urls that the map uses to get its background tiles.

```
DEFAULT_TILES: 'https://url-to-default-map-tiles/{z}/{x}/{y}.png',
HIGH_CONTRAST_TILES: 'https://url-to-high-contrast-map-tiles/{z}/{x}/{y}.png'
```

### i18n
Language specific json files that are used override the default language specific json values.

```
default varaamo en.json:
{
  "HomePage.contentSubTitle": "This is something very specific to city X",
  "HomePage.title": "This is something generic that works for everyone",
  ...
}
en.json from theme
{
  "HomePage.contentSubTitle": "This is now something that city Z needs"
}

final en.json
{
  "HomePage.contentSubTitle": "This is now something that city Z needs",
  "HomePage.title": "This is something generic that works for everyone",
  ...
}
```


### images
**FOLLOWING FILES NAME.EXTENSION MUST BE EXACTLY AS LISTED FOR THEM TO WORK**
 - favicon.ico
    * This one is quite self-explanatory, used instead of the default favicon.
 - homepage.png
    * This is the picture that is used on the home view.
    * A resolution of 1920x800 is recommended.
 - logo_footer.png
    * This is the finnish/default version of the picture that is used in the footer.
 - logo_footer_sv.
    * This is the swedish version of the picture used in the footer.

**FILES BELOW CAN BE ANY NAME.EXT AS THEY ARE ONLY USED IN THE THEMES STYLING**
 - logo.png
   * This is the default/finnish version of the picture that is used in the header.
 - logo_sv.png
   * This is the swedish version of the picture that is used in the header.

### sass
#### main.scss
This file contains all of the custom scss styling that is applied to varaamo.
#### variables.scss
This file contains the scss variables that override the default varaamo scss variables that are found in
`app/assets/styles/_turku.variables`.
