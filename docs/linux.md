# Linux notes

## Aurora/Silverblue

## Aurora/Bluefin package list

<https://github.com/ublue-os/bluefin/blob/main/packages.json>

## Disable autosuspend for usb devices

```shell
sudo rpm-ostree kargs --append=usbcore.autosuspend=-1
```

