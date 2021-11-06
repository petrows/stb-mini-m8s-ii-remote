# Remote configuration for MINI M8S II

I have not found any 100% working `remote.conf` for this STB,
created my own fixed.

Used this instruction: [Create remote.conf from scratch](https://forum.libreelec.tv/thread/3581-create-remote-conf-from-scratch/).

## STB and remote

Remote code is `0x40400001`, but some codes are wrong.



## How to use

Connect to STB using ADB and get shell (you need root, use `su`):

```bash
adb connect stb.pws
adb shell
su
```

In local PC upload this `remote.conf`:

```bash
adb push remote.conf /sdcard/remote.conf
```

Apply changed file in ADB shell:

```bash
mount -o remount,rw /system
cp /sdcard/remote.conf /system/etc/remote.conf
reboot
```
