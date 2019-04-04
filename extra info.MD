# Extra Info

This document provides reasoning for some changes made to the original project, in addition to keeping track of some necessary settings in dokuwiki.

## Changes I made from the original fork

### main.php - New Page and New Folder buttons
I added the following to the main.php file so I can have new page and new sub folder buttons:
```php

 // If URL ends with :start, then it is a folder
if (substr_compare($_SERVER['REQUEST_URI'],':start', strlen($_SERVER['REQUEST_URI'])-strlen(':start')) === 0){

    // create the new string, without the :start
    $url = str_replace(":start","", 'https://' . $_SERVER['SERVER_NAME'] . $_SERVER['REQUEST_URI']);

    // new page button
    echo "<div class='content-actions__action'>";
    echo "<a href=\"#\" rel=\"nofollow\" title=\"Create new page\" onclick=\"var page = prompt('What is the name of the page you would like to create?'); if(page == null || page == ''){} else{ window.location = '$url'+':'+page+'&do=edit'; } \">
        <button class=\"mdl-button mdl-js-button mdl-button--fab mdl-js-ripple-effect mdl-button--colored content-actions__action-button\">
            <i class=\"material-icons\">add</i>
        </button></a>";
    echo "</div>";

    // new sub folder button
    echo "<div class='content-actions__action'>";
    echo "<a href=\"#\" rel=\"nofollow\" title=\"Create new subfolder\" onclick=\"var page = prompt('What is the name of subfolder you would like to create?'); if(page == null || page == ''){} else{ window.location = '$url'+':'+page+':start'+'&do=edit'; } \">
        <button class=\"mdl-button mdl-js-button mdl-button--fab mdl-js-ripple-effect mdl-button--colored content-actions__action-button\">
                <i class=\"material-icons\">create_new_folder</i>
        </button></a>";
    echo "</div>";
}
```


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