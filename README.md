A modified US keyboard layout aimed at programming and the
occasional swedish character.


#### Switched keys
- `<` and `(`
- `>` and `)`

- `åäö` are accessed by `AltGr` + `[';` respectively, ie, where you
  would find the keys on a swedish layout.


#### CapsLock as CTRL
To get rid of the most useless and one of the most prominent
keys on the keyboard, and turn it into something usefult - execute
the registry hack: `caps_lock_to_control.reg`


#### On Linux / where xmodmap is available

```
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

