# Linux notes

## Aurora/Silverblue

## Aurora/Bluefin package list

<https://github.com/ublue-os/bluefin/blob/main/packages.json>

## Disable autosuspend for usb devices

```shell
sudo rpm-ostree kargs --append=usbcore.autosuspend=-1
```

## interactively edit kernel arguments

```shell
sudo rpm-ostree kargs --editor
```
[Source](https://docs.fedoraproject.org/en-US/fedora-coreos/kernel-args/#_interactive_editing)

