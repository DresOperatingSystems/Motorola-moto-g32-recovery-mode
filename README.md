# Motorola-moto-g32-recovery-mode

To get into the spirit of the DresOS systems releasing soon we are releasing a twrp custom recovery mode that you will need for the moto g32 version of DresOS 

What you will need::

WINDOWS:::
Platform tools you can get them for a windows system here

https://developer.android.com/tools/releases/platform-tools

Once you have downloaded the ZIP file to a convenient folder extract it then either open cmd prompt within the folder or go into cmd prompt and make your way to the folder by using the cd cmd then verify installation with adb version if installed correctly then the version number should be showing.

If your device is not detected by ADB or Fastboot, installing the correct USB driver is necessary.
You can get the usb drivers here, 
https://dl-ssl.google.com/android/repository/latest_usb_driver_windows.zip
Download and extract the ZIP file.
Open Device Manager (Win + X → Device Manager).
Locate your Android device under “Other Devices” or “Portable Devices.”
Right-click on the device and select Update Driver.
Choose Browse my computer for drivers and select the extracted driver folder.
Click Next and wait for the installation to complete

LINUX::
We suggest you dont download platform tools the same way as it can be a longer process of setting up depending on the distro you are running so just go into the linux terminal then input this cmd 

sudo apt install adb && sudo apt install fastboot -y 

if this doesnt work then use this cmd 

sudo apt install google-android-platform-tools-installer

Once platform tools have been installed on the system you are using make sure your bootloader is unlocked to do this go into settings then about phone and tap build number several times to unlock dev settings once unlocked go into dev settings enable usb debugging and flick the switch that says OEM UNLOCKING then input into your terminal or cmd prompt adb devices after connecting via usb cable (on windows you will have to be in the platform tools directory) and click allow on the pop up on your phone allowing all the time. Now input adb reboot bootloader to boot your phone into fastboot mode, now input fastboot oem get_unlock_data by executing this cmd you will get a string of numbers/letters so just combine this string into one line by removing the spaces and bootloader word. After that go to the official Motorola website https://en-us.support.motorola.com/app/standalone/bootloader/unlock-your-device-a and login once logged in click on next then put that string in the box and click can my device be unlocked then agree to the terms once you have agreed to the terms you should get an email with the unlock key copy and paste this then go back into your terminal or cmd prompt and input fastboot oem unlock Your_key replace Your_key with the key you got in the email and now your device's bootloader should be successfully unlocked 

Now its unlocked download the twrp zip file from below and extract it on your computer once extracted go to the directory and input fastboot boot TWRP-3.7.1_12-0-devon-202501080743.img to boot your phone into recovery mode (if on windows extract to your platform tools folder)

you can find the recovery mode zip file at the link below
https://mega.nz/file/TF9ymaLB#fSdXsti4tPsDei-cfTf_puzw2m6cx50JsZUdDSUgX_E

DO NOT FLASH IT OR INSTALL IT BECAUSE YOU WILL LOSE ALL DEVICE DATA THIS IS SIMPLY FOR THE FLASH OF THE FUTURE DRESOS SYSTEMS OR IF YOU KNOW WHAT YOU ARE DOING AS THIS DOES PUT YOU INTO THE ROOT OF YOUR DEVICE

You can also use this recovery mode to root your device via magisk using the adb sideload option 

Thank you for using this repository and we hope you stick around for the future releases of the DresOS systems we also do have a DresOS store on the telegram platform where we release apps and other projects so go check it out https://t.me/+3aDyYCtuxNphMjk0

Also any support would be much appreciated so if you could buy us a coffee showing the Dres team some much needed love

https://coff.ee/dresos
