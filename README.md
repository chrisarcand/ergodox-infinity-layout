# Infinity ErgoDox layout and Kiibohd kll compiler

My layout for the [Infinity ErgoDox](http://input.club/devices/infinity-ergodox) keyboard.

### Layer 0 (DefaultMap)

```plaintext
 ,--------------------------------------------------.           ,--------------------------------------------------.
 |   `    |   1  |   2  |   3  |   4  |   5  |  6   |           |  7   |   8  |   9  |   0  |   [  |   ]  |   -    |
 |--------+------+------+------+------+-------------|           |------+------+------+------+------+------+--------|
 |  TAB   |   Q  |   W  |   E  |   R  |   T  |  =   |           |  -   |   Y  |   U  |   I  |   O  |   P  |   \    |
 |--------+------+------+------+------+------|      |           |      |------+------+------+------+------+--------|
 |  ESC   |   A  |   S  |   D  |   F  |   G  |------|           |------|   H  |   J  |   K  |   L  |   ;  |   '"   |
 |--------+------+------+------+------+------|  ƒ1  |           |  ƒ1  |------+------+------+------+------+--------|
 | LSHIFT |   Z  |   X  |   C  |   V  |   B  |      |           |      |   N  |   M  |   ,  |   .  |   /  | RSHIFT |
 `--------+------+------+------+------+-------------'           `-------------+------+------+------+------+--------'
   | LGUI |script|  ƒ2  | LALT | LGUI |                                       | RGUI | RALT | RCTRL| PrevL| NextL|
   `----------------------------------'                                       `----------------------------------'
                                  ,-----------------.       ,-----------------.
                                  | LGUI+[ | LGUI+] |       |  LEFT  |  RIGHT |
                           ,------+--------+--------|       |--------+--------+------.
                           |      |        |  HOME  |       |   UP   |        |      |
                           | Bksp | LCTRL  |------  |       |--------| ENTER  | SPACE|
                           |      |        |  END   |       |  DOWN  |        |      |
                           `------------------------'       `------------------------'
```

* `script` is my [`:Hashrockets` vim command](https://github.com/chrisarcand/dotfiles/blob/a80ee91c8b15b601e3c96a4106dcf02f2a99edda/vim/vimrc.symlink#L306-L323)
* `PrevL`    : `PREV LAYER`
* `NextL`    : `NEXT LAYER`
* `ƒ1`       : `FUN1` (hold for Layer 1)
* `ƒ2`       : `FUN2` (hold for Layer 2)
* `LGUI+[/]` : Browser back/forward buttons!

### Layer 1

```plaintext
 ,--------------------------------------------------.           ,--------------------------------------------------.
 |        |  F1  |  F2  |  F3  |  F4  |  F5  |      |           |      |  F6  |  F7  |  F8  |  F9  | F10  |  F11   |
 |--------+------+------+------+------+-------------|           |------+------+------+------+------+------+--------|
 |        |  !   |  @   |  {   |  }   |  |   |      |           |      |NUMLCK|  P7  |  P8  |  P9  |  P-  |  F12   |
 |--------+------+------+------+------+------|      |           |      |------+------+------+------+------+--------|
 |        |  #   |  $   |  (   |  )   |  &   |------|           |------|CAPSLK|  P4  |  P5  |  P6  |  P+  |        |
 |--------+------+------+------+------+------|      |           |      |------+------+------+------+------+--------|
 |        |  %   |  ^   |  [   |  ]   |  ~   |      |           |      |      |  P1  |  P2  |  P3  |  P/  |        |
 `--------+------+------+------+------+-------------'           `-------------+------+------+------+------+--------'
   |      |      |      |      |      |                                       |  P0  |  P.  |  P=  | PrevL| NextL|
   `----------------------------------'                                       `----------------------------------'
                                  ,-----------------.       ,-----------------.
                                  |        |        |       |        |        |
                           ,------+--------+--------|       |--------+--------+------.
                           |      |        |        |       |        |        |      |
                           |      |        |------  |       |--------|        |      |
                           |      |        |        |       |        |        |      |
                           `------------------------'       `------------------------'
```

### Layer 2

```plaintext
 ,--------------------------------------------------.           ,--------------------------------------------------.
 |   B+   |      |      |      |      |      |      |           |      |      |      |      |      |      |   V+   |
 |--------+------+------+------+------+-------------|           |------+------+------+------+------+------+--------|
 |   B-   |      |      |  UP  |      |      |      |           |      |      |      |      |      |      |   V-   |
 |--------+------+------+------+------+------|      |           |      |------+------+------+------+------+--------|
 |        |      | LEFT | DOWN | RIGHT|      |------|           |------|      |      |      |      |      |  MUTE  |
 |--------+------+------+------+------+------|      |           |      |------+------+------+------+------+--------|
 |        |      |      |      |      |      |      |           |      |      |      |      |      |      |  PL/PS |
 `--------+------+------+------+------+-------------'           `-------------+------+------+------+------+--------'
   |      |      |      |      |      |                                       |      |      |      | PrevL| NextL|
   `----------------------------------'                                       `----------------------------------'
                                  ,-----------------.       ,-----------------.
                                  |        |  FLASH |       |  FLASH |        |
                           ,------+--------+--------|       |--------+--------+------.
                           |      |        |        |       |        |        |      |
                           |      |        |--------|       |--------|        |      |
                           |      |        |        |       |        |        |      |
                           `------------------------'       `------------------------'
```

* `B+` : Screen brightness increment
* `B-` : Screen brightness decrement

### BaseMap

This is the layer from which _all_ trigger layers are derived from. **This is not the DefaultMap (Layer 0).**

> The reason for everything being based off of the BaseMap is because all .kll
> files can then assume QWERTY is the base. Significantly simplifies layer
> portability. This way you can define Colemak or Dvorak once and it will work
> for every single Infinity keyboard.

```plaintext
 ,--------------------------------------------------.           ,--------------------------------------------------.
 |   =    |   1  |   2  |   3  |   4  |   5  | ESC  |           | fnc6 |   6  |   7  |   8  |   9  |   0  |   -    |
 |--------+------+------+------+------+-------------|           |------+------+------+------+------+------+--------|
 |   \    |   Q  |   W  |   E  |   R  |   T  | fnc1 |           |  [   |   Y  |   U  |   I  |   O  |   P  |   ]    |
 |--------+------+------+------+------+------|      |           |      |------+------+------+------+------+--------|
 |  TAB   |   A  |   S  |   D  |   F  |   G  |------|           |------|   H  |   J  |   K  |   L  |   ;  |   '"   |
 |--------+------+------+------+------+------| fnc2 |           | fnc7 |------+------+------+------+------+--------|
 | LSHIFT |   Z  |   X  |   C  |   V  |   B  |      |           |      |   N  |   M  |   ,  |   .  |   /  | RSHIFT |
 `--------+------+------+------+------+-------------'           `-------------+------+------+------+------+--------'
   | LGUI |   `  | fnc3 | fnc4 | fnc5 |                                       | LEFT | DOWN |  UP  | RIGHT| RGUI |
   `----------------------------------'                                       `----------------------------------'
                                  ,-----------------.       ,-----------------.
                                  | LCTRL  |  LALT  |       |  RALT  |  RCTRL |
                           ,------+--------+--------|       |--------+--------+------.
                           |      |        |  HOME  |       |  PgUp  |        |      |
                           | Bksp | DELETE |------  |       |--------| ENTER  | SPACE|
                           |      |        |  END   |       |  PgDn  |        |      |
                           `------------------------'       `------------------------'
```

Keys marked in CAPS above are how they are specified in the .kll file. Other key identifiers include:

* `FUNCTION*` : Function keys, identified as `fnc*` above
* `BACKSPACE` : Identified as `Bksp` above
* `PAGEUP`    : Identified as `PgUp` above
* `PAGEDOWN`  : Identified as `Pgdown` above
* `EQUALS`    : `=`
* `MINUS`     : `-`
* `BACKSLASH  : `\`
* `LBRACE`    : `[`
* `RBRACE`    : `]`
* `SEMICOLON` : `;`
* `QUOTE`     : `'"`
* `COMMA`     : `,`
* `PERIOD`    : `.`
* `SLASH`     : `/`
* `BACKTICK`  : `'`

This is the list of keys you map _from_ the base layer; the list of key codes you can map _to_ is extensive
and found at https://input.club/configurator-ergodox/

## Editing

The layout files are in kiibohd/*.kll.

## Workflow

My workflow uses the [dockerized version](https://hub.docker.com/r/fmerizen/ergodox-infinity-layout/) of the KLL compiler. First make sure that you have a working docker installation.

1. Edit `layer-*.kll` files to your liking
2. If layers are added or removed, you must change the value of PartialMaps in `kiibohd/build.bash` accordingly
3. Run `./compile.sh default.bash` from a docker aware bash
4. The compiled firmware is now available as `kiibohd/*.dfu.bin`
5. Flash the keyboard with [dfu-util](https://github.com/kiibohd/controller/wiki/Loading-DFU-Firmware)
