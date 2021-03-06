# CSS Guideline

## CSS Folders
Root folder should only contain CSS-files that would be compiled. Other files should be placed in folders. Example:


    partials/
      layout.css.scss
      typography.css.scss
      forms.css.scss
      elements.css.scss
    views/
      contacts.css.scss
      blog.css.scss
    blocks/
      welcome.css.scss
    libs/
      jquery.fancybox.css.scss
      jquery.chosen.css.scss
    application.css.scss
    admin.css.scss
    pages.css.scss

## CSS Syntax
1. Charset should be declared in the beginning of top file: ```@charset "utf-8";```
2. Only @import can be used in the files - they will be automatically compiled into one file without imports later. This is needed for most of the CSS libs that are used as a Gems, so begin project with @import so later you won't rewrite main files again: ```@import "partials/layout";```
3. Place all the SaSS vars in one file: ```partials/setup.css.scss```
4. No need to use prefixes (especially mixins for them) for old selectors such as border-radius, box-shadow
5. External @font-face (from [Google Fonts](https://google.com/fonts), for example) shouldn’t be used via ```@import``` & must be used as external CSS file right before main stylesheet file


## Frameworks

### [DroidCSS](https://github.com/droidlabs/droidcss)
DroidCSS is a small CSS Framework that contains most of the Bourbon mixins & Grid Generator.

1. DroidCSS should be used only as a [Gem file](http://rubygems.org/gems/droidcss): ```droidcss```

### [Bourbon](https://github.com/thoughtbot/bourbon)
Most popular Gem for SaSS mixins.

1. Bourbon should be used only as a [Gem file](http://rubygems.org/gems/bourbon): ```bourbon```

### [Bootstrap](https://github.com/twbs/bootstrap-sass)
Most popular CSS Framework by Twitter.

1. In RoR projects Twitter Bootstrap should be used only as a [Gem file](http://rubygems.org/gems/bootstrap-sass) (Twitter Bootstrap should be easily updated via Gem): ```bootstrap-sass```
2. Theme variables should be used as much as possible to modify theme. All variables should be collected in one file.
3. All overrides and additions to the Twitter Bootstrap styles should be placed in the bootstrap folder: ```stylesheets/theme/bootstrap```. Each filename should be the same as filename in Bootstrap Framework. 
4. Only project required JS libs for Twitter Bootstrap should be used. Do not require all libs or use bootstrap.min.js files (they can be included only if all the JS libs are needed in the project).
5. [Bourbon](#bourbon) might be needed for mixins since Twitter Bootstrap doesn't have a lot of mixins that are commonly used around projects.
