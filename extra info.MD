# Extra Info

This document provides reasoning for some changes made to the original project, in addition to keeping track of some necessary settings in dokuwiki.

## Changes I made from the original fork

### css/basic.less
I added this to disable top level headers in content files, but not admin UIs
```css
.content-card__text > .sectionedit1 {
  display:none;
}
```

### sidebar.php
I commented out some stuff that I didn't need. It is labeled in the file.

### conf/default.php
I set these to my preferred preferences.

### style.ini
I changed the default theme to a custom blue.

## Doku Wiki Settings
Set ```breadcrumbs``` to ```0```

Set ```youarehere``` to enabled.