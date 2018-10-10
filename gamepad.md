# Gamepad config

Mapping Rockfire USB controller with xboxdrv

```
sudo xboxdrv \
  --evdev /dev/input/by-id/usb-Padix_Co._Ltd._Rockfire_USB_SmartTraveller-event-joystick \
  --evdev-debug \
  --evdev-absmap ABS_X=x1,ABS_Y=y1 \
  --axismap -Y1=Y1 \
  --ui-axismap x1^cal:-30000:-14000:-2768,y1^cal:-30000:-14000:-2768= \
  --evdev-keymap BTN_TRIGGER=a,BTN_THUMB=b,BTN_THUMB2=x,BTN_TOP=y,BTN_TOP2=lb,BTN_PINKIE=rb,BTN_BASE=back,BTN_BASE2=start \
  --deadzone 6000
```
