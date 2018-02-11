Notes about DZ60 PCB based keyboard with hhkb layout

* put the keyboard in boot mode

- stock firmware was SPC+b
- default dz60 is Fn+Backspace (row 2)

When in boot mode, dmesg should output something like

[ 2856.077254] usb 1-7: new full-speed USB device number 12 using xhci_hcd
[ 2856.205268] usb 1-7: New USB device found, idVendor=03eb, idProduct=2ff4
[ 2856.205274] usb 1-7: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[ 2856.205279] usb 1-7: Product: ATm32U4DFU usb 1-7: Manufacturer: ATMEL
[ 2856.205286] usb 1-7: SerialNumber: 1.0.

Last change option : short pin 13 (reset) with GND (23 was easy to reach)

* reprogram the keyboard

sudo dfu-programmer atmega32u4 erase
sudo dfu-programmer atmega32u4 flash /path/to/_name_file.hex
sudo dfu-programmer atmega32u4 start
