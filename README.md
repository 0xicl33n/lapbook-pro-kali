# lapbook-pro-kali
This is a collection of files / scripts for helping users with their generic 7 inch mini laptop from some obscure chinese company.

## Issues

| Working?      |     |
| ------------- |:---:|
| Audio         | ❌   |
| Touchscreen   | ❌   |
| Mouse         | 🚧  |
| GRUB portrait | 🚧  |
| Laptop lid    | ❔   |

## Stuck in portrait mode? 
`xrandr -o right` 

## Mouse not working?
The mouse buttons are actually KEYBOARD KEYS. They will have to be macro'd:

- `KP_Begin` => left click 
- `MENU` => right click

You can use either `input-remapper` or `xdotool`. 

The keycode for `KP_Begin` is `84` and `xmodmap` key `0xFF9D`.
The keycode for `MENU` is  `117` and `xmodmap` key `0xFF67`.

The mouse nib itself is an `HTIX5288` which is known to have problems as of kernel 5.4.

## Whats the Kernel?
wip
