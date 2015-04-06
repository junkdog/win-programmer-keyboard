A modified US keyboard layout aimed at programming and the occasional swedish character.
Works with modern windows versions, including 8.1.

[Microsoft Keyboard Layout Creator](http://www.microsoft.com/en-us/download/details.aspx?id=22339) was
used to create the layout and compile the installation package.


## Installing
Run `setup.exe` and, optionally, `caps_lock_to_control.reg`. Restart the computer (might suffice
to logout/login, I haven't tried it).

The keyboard layout  should be automatically added to `Control Panel / Language / Language
Options / Input Method`.
If its not, manually add `United States-Junkdog`.


## Changed keys
Changed and switched keys are highlighted. All other keys are standard US layout.


#### With Shift
![with shift](https://github.com/junkdog/win-programmer-keyboard/raw/master/images/layout-shift.png)


#### With AltGr / Right Alt
The additional swedish characters, åäö/ÅÄÖ, occupy the keys matching the swedish layout.

![with shift](https://github.com/junkdog/win-programmer-keyboard/raw/master/images/layout-altgr.png)


## CapsLock as CTRL
CapsLock - the least useful, but also most prominent key - has never done
a good deed or earned its keep. Since we care and don't give up on keys gone astray,
we can help it by nudging it in the right direction via a registry hack:
`caps_lock_to_control.reg`


## Other useful stuff
- [AltDrag](https://stefansundin.github.io/altdrag/) emulates X11's ALT+LMB to move and ALT+RMB
  to resize windows. It also has a few other tweaks.
- [Launchy](http://www.launchy.net/), slick application launcher.

## On Linux / where xmodmap is available
What originally started my frustration. Note that on linux, your desktop environment
of choice usually has the option of mapping the CapsLock key to CTRL, without the
need of going through xmodmap - the snippet below doesn't remap CapsLock.

```bash
# copied from my .bashrc
if hash xmodmap &> /dev/null ; then
    xmodmap -e "keysym ISO_Level3_Shift = Mode_switch"
    xmodmap -e "keycode 34 = bracketleft braceleft aring Aring"
    xmodmap -e "keycode 47 = semicolon colon odiaeresis Odiaeresis"
    xmodmap -e "keycode 48 = apostrophe quotedbl adiaeresis Adiaeresis"

    xmodmap -e "keycode 59 = comma parenleft"
    xmodmap -e "keycode 60 = period parenright"
    xmodmap -e "keycode 18 = 9 less"
    xmodmap -e "keycode 19 = 0 greater"
fi
```

