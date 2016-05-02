# custom-xkb
Custom XKB layouts for special keyboards

# Topre 23U
Makes the = button work correctly. The button normally sends `Alt+KP_6+KP_1`, which is great if you're on Windows, not so great on anything else. This layout maps the keypad's `Alt` to `AltGr`, `AltGr+KP_6` to `KP_Equal`, and `AltGr+KP_1` to nothing (`VoidSymbol`). Thus, pressing the = button on the keypad will actually produce a =. 

# Symbiosis
Provides mappings for the alternate symbols on SP's Symbiosis keyset, accessed through AltGr/Right Alt. A few keys have a fourth symbol accessed via Shift+AltGr. 

# How to Use
To use these, first take the `xkbmap` file in the folder of the desired keyboard and append it to the end of your `/usr/share/X11/xkb/symbols/us_sym`. Make a backup of the file just in case. 
First, test the layout by doing `setxkbmap -device n -layout us -variant (sym|toprenumpad)`, where `n` is the device ID you want to apply the layout to as shown in `xinput`. Make sure the layout works as expected. This is not permanent, so assuming everything worked, you'll want to put it in your Xorg conf (see below). 
Review the contents of the `xorg` file, and selectively add the contents to your `xorg.conf` or `xorg.conf.d`. Restart your X server to see the changes and ensure everything is working fine. 

# Hey, There's a Better Way To Do This
There probably is, xkb isn't exactly the pinnacle of documentation. Feel free to let me know if there's a cleaner way of doing something. 
