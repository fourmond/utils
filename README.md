utils
=====

Various utility scripts

## `make-theme-image`

`make-theme-image` extracts the icons from a debian theme package and
presents them using image magick. It can work on an already downloaded
package file (just give the file name), or use `dget` to get it, and
caches the icons in a `.cache` subdirectory.

Try it out this way, for instance:

```
~ make-theme-image oxygen-icon-theme
```

You can choose the icons to use using the `-w` (specify) and `-a`
(add) options, based on their name in the [freedesktop icon specs](https://standards.freedesktop.org/icon-naming-spec/icon-naming-spec-latest.html).
Not all the icons are provided by each package.

To make thumbnails for **all** icon theme packages, try this:

```
apt search -- -icon-theme | grep / | cut -d/ -f1 | xargs make-theme-image
```


## `trim-odt`

`trim-odt` is a simple shell script that removes thumbnails from Libreoffice files.

```
~ trim-odt my-document.odt
```
