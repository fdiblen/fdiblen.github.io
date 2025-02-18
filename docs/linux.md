# Linux notes

## Aurora/Silverblue

Disable autosuspend for usb devices

```shell
sudo rpm-ostree kargs --append=usbcore.autosuspend=-1
```
