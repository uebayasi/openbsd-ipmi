# openbsd-ipmi
OpenBSD's ipmi(4) changes to support /dev/ipmi*

kernel
```
git clone .../openbsd-ipmi.git
cd openbsd-ipmi
git diff ipmi19-base ipmi19 >/tmp/ipmi.patch
cd .../src
patch -p1 </tmp/ipmi.patch
```

ipmitool (sysutils/ipmitool)
- Apply the patch (```ipmitool.patch```), build, and install
- Create /dev/ipmi0 by ```doas mknod -m 0600 /dev/ipmi0 c 93 0```
- Try commands
  - ```ipmitool chassis status```
  - ```ipmitool sdr```
  - ```ipmitool sel elist```
