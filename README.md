# oplus_nord_ce5-magisk
Magisk patched init_boot images for OnePlus Nord CE5 

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

### Flashing root
**You must firstly unlock bootloader and setup your device again before flashing root**
