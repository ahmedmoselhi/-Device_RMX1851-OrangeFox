# android_device__RMX1851
For building SHRP for Realme 3 Pro

TWRP device tree for Realme 3 Pro originally by mauronofrio

## Features

Works:

- ADB
- Decryption of /data
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG
- Vibration support
## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/SKYHAWK-Recovery-Project/platform_manifest_twrp_omni.git -b 9.0

repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/realme/RMX1851" name="ahmedmoselhi/SHRP_Device_RMX1851" remote="github" revision="android-9.0" />
```

Finally execute these:

```
export ALLOW_MISSING_DEPENDENCIES=true; source build/envsetup.sh; lunch omni_RMX1851-eng; mka recoveryimage
```

To test it:

```
fastboot boot out/target/product/RMX1851/recovery.img
```
## Other Sources

Kernel Sources:https://github.com/HyperTeam/android_kernel_realme_sdm710
