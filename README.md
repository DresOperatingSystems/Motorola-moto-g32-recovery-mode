# Motorola Moto G32 Recovery Mode

This guide explains how to install platform tools, unlock the bootloader and boot into TWRP recovery mode on your Motorola Moto G32. **Warning:** Unlocking the bootloader will wipe your device data. Proceed with caution and back up your data first.

## Prerequisites

- A USB cable to connect your phone to your computer.
- Enable USB debugging and OEM unlocking on your device:
  1. Go to Settings > About phone.
  2. Tap "Build number" 7 times to enable Developer options.
  3. Go back to Settings > System > Developer options.
  4. Enable "USB debugging" and "OEM unlocking".

## Installing Platform Tools

### Windows

1. Download the platform tools from the official Android site: [https://developer.android.com/tools/releases/platform-tools](https://developer.android.com/tools/releases/platform-tools).
2. Extract the ZIP file to a convenient folder (e.g., `C:\platform-tools`).
3. Open a Command Prompt in that folder (hold Shift + right-click in the folder and select "Open command window here" or navigate via `cd`).
4. Verify installation:

   ```bash
   adb version
   ```

   This should display the ADB version number.

If your device isn't detected by ADB or Fastboot install USB drivers:

1. Download the USB drivers: [https://dl-ssl.google.com/android/repository/latest_usb_driver_windows.zip](https://dl-ssl.google.com/android/repository/latest_usb_driver_windows.zip).
2. Extract the ZIP file.
3. Open Device Manager (Win + X > Device Manager).
4. Locate your Android device under "Other Devices" or "Portable Devices."
5. Right-click the device > Update Driver > Browse my computer for drivers.
6. Select the extracted driver folder and click Next.

### Linux

Install platform tools via your package manager (for Debian based distros like Ubuntu):

```bash
sudo apt update
sudo apt install adb fastboot -y
```

If that doesn't work try:

```bash
sudo apt install google-android-platform-tools-installer
```

For other distros refer to your package manager (e.g., `yum` or `dnf` for RPM-based systems).

## Unlocking the Bootloader

1. Connect your phone to your computer via USB.
2. In your terminal or Command Prompt (navigate to platform-tools folder on Windows):

   ```bash
   adb devices
   ```

   Authorize the connection on your phone (select "Always allow from this computer").

3. Reboot to bootloader:

   ```bash
   adb reboot bootloader
   ```

4. Get the unlock data:

   ```bash
   fastboot oem get_unlock_data
   ```

   Combine the output into a single string (remove spaces and "bootloader" words).

5. Go to the official Motorola bootloader unlock site: [https://en-us.support.motorola.com/app/standalone/bootloader/unlock-your-device-a](https://en-us.support.motorola.com/app/standalone/bootloader/unlock-your-device-a).
6. Log in click next then paste the string and check if your device can be unlocked.
7. Agree to the terms; you'll receive an unlock key via email.
8. Unlock the bootloader (replace `YOUR_UNLOCK_KEY` with the key from the email):

   ```bash
   fastboot oem unlock YOUR_UNLOCK_KEY
   ```

   Your device will reboot and wipe data.

## Booting into TWRP Recovery

1. Download the TWRP image from this repository: 
2. Place the image in your platform-tools folder (or current directory).
3. Boot into the recovery (ensure you're in bootloader mode):

   ```bash
   fastboot boot TWRP-3.7.1_12-0-devon-202501080743.img
   ```

**Important:** Do NOT flash or install the TWRP image permanently, as it will wipe your device data. This is only for temporary booting into recovery for tasks like flashing custom ROMs or advanced operations.

## Additional Uses

- **Rooting with Magisk:** In TWRP use the ADB sideload option to install Magisk for root access.
- If you know what you're doing, this recovery provides root-level access to your device.

**Disclaimer:** These steps involve risks that could end up bricking your device. Use at your own risk. Ensure you're following the latest official guides for your specific device model.

Thank You 

The DresOS Team

check out our website here: https://dresoperatingsystems.github.io/
