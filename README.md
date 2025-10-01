# oplus_nord_ce5-magisk
Magisk patched init_boot images for OnePlus Nord CE5 

**Magisk Version: *29.0***

**I'm not responsible for any damage caused to your device.**

## Structure
VERSION_REGION.init_boot.img

#### Example
```
CPH2719_15.0.2.601_EX01_GLO.init_boot.img

Version: CPH2719_15.0.2.601_EX01
Region: GLOBAL
```

**You must flash EXACT version of patched init_boot or you might brick your device.**

## Tutorial
Tutorial for rooting OnePlus Nord CE5

#### Prerequisites
* Ability to read and understand instructions
* Device that supports OEM unlocking (not carrier locked device)
* >50% charge

### Unlocking Bootloader
**You must unlock bootloader before flashing rooted init_boot.img**

1. Enable [Developer Options](https://developer.android.com/studio/debug/dev-options#enable)
2. Enable *USB Debugging* and *OEM Unlocking* in *Developer Options*
3. Install [adb and fastboot](https://developer.android.com/tools/adb) on PC
4. Connect your device to PC via USB and approve USB debugging for your PC
5. Backup your data (you may skip this step if your OnePlus Nord CE5 has no important data / you just finished setting and you still have data saved)
   ```bash
   adb pull <path/to/directory/on/android>
   ```
   **User data is stored in /sdcard**
6. Reboot into fastboot
   ```bash
   adb reboot bootloader
   ```
7. Unlock bootloader
   ```bash
   fastboot flashing unlock
   ```
   Your device would show instructions to unlock / abort unlocking bootloader. Click *Volume Up* to approve. It would display result right after that. If everything is successful enter
   ```bash
   fastboot reboot
   ```
8. Setup your device again

*If bootloader is successfully unlocked **Developer Options** > **OEM Unlocking** should be greyed out and enabled*

### Flashing root
**You must firstly unlock bootloader and setup your device again before flashing root**

1. Download [Magisk Manager APK](https://github.com/topjohnwu/Magisk) and install it
   **Download it only from official github releases**
2. Enable *Developer Options* and *USB Debugging*
3. If your firmware version has no patched init_boot.img
    1. Try upgrading it to latest publically available firmware version (check update version via System Updates)
       *Check 4pda / xda for firmware versions*
       *You might have to sideload OTA*
    3. Try using [Oxygen Updater](https://play.google.com/store/apps/details?id=com.arjanvlek.oxygenupdater)
    4. Try downgrading manually to latest available version
  
       *You need full OTA .zip file and tools like payload-dumper to extract init_boot.img from payload.bin in OTA .zip*
       *After getting stock init_boot.img send it to android device after installing Magisk Manager and patch init_boot.img; then send patched init_boot.img back to PC*
4. Select patched init_boot.img that matches version of firmware downloaded on your device (also check if firmware region matches)
   **If version of init_boot.img doesn't match your device firmware version your device might be bricked**
5. Connect your device to PC via USB and approve debugging
6. Reboot to fastboot
   ```bash
   adb reboot bootloader
   ```
7. Flash init_boot.img
   ```bash
   fastboot flash init_boot <path/to/init_boot.img>
   ```
    After flashing init_boot.img reboot your device
   ```bash
   fastboot reboot
   ```
