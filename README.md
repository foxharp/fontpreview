<!-- doit: python3 -m markdown < README.md >README.html
-->

# fontpreview

This previewer started as a clone of
<https://github.com/sdushantha/fontpreview>,
written by github user sdushantha.  They created a clever mechanism
for quickly getting a look at the contents of a font, in an easy to
navigate way.  It's not clear that the original project is still being
maintained, so I've kind of had my way with the code, and it's diverged
quite a bit.  The rest of the README describes my version, though from
a high level it's still pretty similar to sdushantha's.

__fontpreview__ lets you quickly search through installed fonts using
the __fzf__ "fuzzy matcher", and preview them.  The previewer (any of
__sxiv__, __nsxiv__, or __feh__ will work) is normally reused for each
new font, but it's also possible to bring up a separate preview for
every selection. 

![Animated screen showing fontpreview in use](extra/demo.gif)

## Dependencies

Things you might need to fetch from your package manager:

- xdotool
- fzf
- imagemagick
- nsxiv, sxiv, or feh


## Usage Summary

    Interactive usage:
        fontpreview [--size WxH ] [--position +X+Y ]
                    [--bg-color <colorspec> ] [--fg-color <colorspec> ]
                    [--font-size <pixels> ] [--preview-text <text> ]
                    [--no-preview-header ] [--multi-viewer ]
     
       --multi-viewer           spawn new viewer per font.  (clean up manually.)
       --size WxH               width and height in pixels
       --position +X+Y/-X-Y     position, in X geometry notation (see "man X")
       --font-size              font size for the preview window
       --bg-color,--fg-color    colors for the preview window
       --preview-text           text to be previewed
       --no-preview-header      don't include the font name in the preview

    One-shot usage (most interactive options still apply):
        To preview a font from its file (.otf, .ttf, .woff):
            fontpreview <fontfile>
        To preview a font into an image file:
            fontpreview <fontfile> <imagefile>


## Installation
Simply download the script, make it executable, and put it in your
PATH somewhere.


## Customization

Hey, it's a shell script -- customize all you want.  ;-)  If you
just want to change some of the predefined defaults for color, size,
etc, there's provision for putting those new definitions into
`~/.fontpreview`.  See the script for the names of the variables
that can be changed in that way.
