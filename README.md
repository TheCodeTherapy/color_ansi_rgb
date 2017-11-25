# color_ansi_rgb

This is a small class that I wrote to be able to handle **ANSI escape code** on gnome-terminal / mate-terminal without importing fancy libs with lots of stuff that I don't actually need. It should work fine on any terminal emulator with 256 colors support as it basically handle ANSI escape codes. It can convert hexadecimal RGB values (as in *#FF3100*) into the closest ANSI value available, so you can use RGB colors to print to the terminal.

As I just needed to be able to handle foreground/background colors and font decoration I focused on that and wrote some methods to control it as straightforwardly as I could.

To handle all the possible colors, the class basically generates the 216 values in a 6x6x6 predefined ANSI cube matrix as per it's pre-determined value increments, besides attributing the standard ANSI values for the 16 basic colors and 16 shades of gray.

Available text styles are:
* 'normal'
* 'bold'
* 'dim'
* 'italic'
* 'underline'
* 'blink' **(\*)**
* 'reverse'

**NOTE\*:** *Fortunately* most modern terminals and terminal emulators do not support blinking text style anymore. I added the escape sequence to control that though, as it's escape code may be implemented as an alternative looking highlighting style by some terminal emulators. On gnome-terminal or mate-terminal it will just show regular text.

#### TO DO (when more free/bored time reveals itself available :):
1. rewrite it with a test driven mindset.
1. document it
1. ?optimize the closest_rgb method as it feels a little bit *hackish* right now
