# Philips_monitor_control
Python command line tool to control the Philips BDM4065UC monitor (and possibly others).

# How to use
* Connect your monitor to a RS-232 serial port on your computer.
* Export an enverionment variable with the serial port your screen is connected to: `export PHILIPS_MONITOR="/dev/ttyX"` 
* Place the tool somehwere on your path, like `/usr/bin` (optional)

# Commands
All commands below may be combined.

## Configuration settings
* `dispcon --port PORT`                              - Override any port present in your environment

## Getters:
* `dispcon settings`                                 - Show current display settings
* `dispcon serial`                                   - Show monitor serial number
* `dispcon platform`                                 - Show SICP platform revision
* `dispcon sources`                                  - Show current video input sources
* `dispcon help`                                     - Show the current help menu
 
## General settings:
* `dispcon b X`                                      - set (b)rightness to X %
* `dispcon b i X`                                    - set (i)ncrease (b)rightness with X %point
* `dispcon c X`                                      - set (c)ontrast to X %
* `dispcon s X`                                      - set (s)harpness to X %
* `dispcon source I`                                 - set the video input to I
    Supported inputs are 'vga', 'hdmi', 'hdmi2', 'dvi', 'dp' and 'mdp'.
 
## Subwindow configuration:
* `dispcon sub type T`                               - set Subwindow type to T.
    Supported types are 'pip', '1'='off', '2', '3' and '4'.
    Type 2, 3 and 4 display inputs side-by-side.
* `discpcon sub off`                                 - disable subwindow
* `dispcon sub source O I`                           - set source of Subwindow O to I.
    Supported Subwindows are '1'='pip', '2' and '3'.
    Supported inputs are 'vga', 'hdmi', 'hdmi2', 'dvi', 'dp' and 'mdp'.
* `dispcon sub type T source O1 I1 source O2 I2 ...` - combination to quickly set types and sources
