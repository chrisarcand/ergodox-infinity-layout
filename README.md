# Infinity ErgoDox layout and Kiibohd kll compiler

My layout for the [Infinity ErgoDox](http://input.club/devices/infinity-ergodox) keyboard.

## Editing

The layout files are in kiibohd/*.kll.

## Workflow

My workflow uses the [dockerized version](https://hub.docker.com/r/fmerizen/ergodox-infinity-layout/) of the KLL compiler. First make sure that you have a working docker installation.

1. Edit `layer-*.kll` files to your liking
2. If layers are added or removed, you must change the value of PartialMaps in `kiibohd/build.bash` accordingly
3. Run `./compile.sh default.bash` from a docker aware bash
4. The compiled firmware is now available as `kiibohd/*.dfu.bin`
5. Flash the keyboard with [dfu-util](https://github.com/kiibohd/controller/wiki/Loading-DFU-Firmware)
