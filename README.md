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

    usage:

     fontpreview [options] <fontfile>
        to preview a font from its file (.otf, .ttf)

     fontpreview [options] <fontfile> <imagefile>
        to create an image from the preview

     fontpreview [options]
        interactive use

     Options:
       -text                   text to be previewed
       -font-size              font size for the preview window
       -no-preview-header      don't include the font name in the preview
       -multi-viewer           spawn new viewer per font.  (clean up manually.)
       -bg-color <colorspec>   background color for the preview window
       -fg-color <colorspec>   foreground color for the preview window
       -size WxH               width and height in pixels (overrides autosizing)
       -position +X+Y/-X-Y     position, as in X geometry (see "man X")

       All options can be shortened to the first character of each word in
           the option:  e.g., '-fs' for '-font-size', or '-t' for '-text'.
           (Or, reduced to the the shortest unique prefix.)
       Either '-' or '--' can introduce any option.


## Installation
Simply download the script, make it executable, and put it in your
PATH somewhere.  To download from github, click on the script "fontpreview",
then use the "hamburger" menu or ctrl-shift-s to download it.  You'll need
to "```mv fontpreview.txt fontpreview```" after it's downloaded.

## Customization

Hey, it's a shell script -- customize all you want.  ;-)  If you
just want to change some of the predefined defaults for color, size,
etc, there's provision for putting those new definitions into
`$HOME/.fontpreview`.  See the script for the names of the variables
that can be changed in that way.
