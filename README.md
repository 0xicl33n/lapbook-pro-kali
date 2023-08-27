# lapbook-pro-kali
This is a collection of files / scripts for helping users with their generic 7 inch mini laptop from some obscure chinese company.

## Issues

| Working?      |     | Notes                                                    |
| ------------- |:---:| --------------------------------------------------------:|
| Audio         | ✅   |                                                          |
| Touchscreen   | ❌   | Not even detected                                        |
| Mouse         | 🚧  | Still not satisfied with the remapping                   |
| GRUB portrait | 🚧  | GRUB option `fbcon` ignored for menu but the rest is not |
| Laptop lid    | ❔   | Seems to work but locks up with `i3lock`                 |

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
At the time of this writing it is kernel 3.6.0 with an attempt at better framebuffer support to fix GRUB see: https://docs.kernel.org/fb/fbcon.html

## Audio 
- Ensure `alsamixer`, `aplay` and `firmware-sof-signed` are installed. 
- Mess arounc with pulse settings (in xfce or something). Make sure theyre all up and not muted
- Terminal > `echo "options snd_soc_sof_es8336 quirk=0x02" >> /etc/modprobe.d/alsa-base.conf`
- Reboot
- Run `alsamixer -c 0`
- Mess with the sliders until you hear audio. Mostly the `Speakers` slider