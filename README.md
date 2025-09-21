# WX3in1Plus2.0
Modified version of the WX3in1 Plus 2 Configurator v1.13

Name: WX3in1 Plus 2 Configurator v1.13x.exe<br>
Size: 1981952 bytes : 1935 KiB<br>
SHA1: 73f499e660767005e34a7053fc5860a8c5983007<br>
SHA256: fad4ae63ef51de8f8eb24de96a96ced11c7ee948c5a2e3882354f77114d84d36<br>

These are the modifications I made to the original configurator to assist me setting up and experimenting with my WX3in1 Plus 2.0 device. It relaxes some of the time constraints imposed on the TX delay and beaconing settings by the original configurator.
  
- When experimenting with the WX3in1, waiting around for the device to beacon every 5 minutes can sometimes be quite time-consuming.<br>
  All beacon settings now allow a 1 minute minimum rather than 5 minutes.<br>
  All range error messages changed from "(5 - 1440) to "(max 1440)"<br>
- Changed "Radio" tab "TX delay [ms]" setting to allow delays down to 100ms.<br>
  Range error message changed from "(200 - 1000) to "(100 - 1000)"<br>
  Note: The WX3in1 web interface allows a TX delay all the way down to 0 if you want to further experiment!<br>

<i>Note: These changes were made by reverse engineering and hand-patching the original .exe binary.</i><br>
These are not official changes. Use at your own risk.<br>

You must use the author's original utility to configure your unit before going live.<br>
https://microsat.com.pl/product_info.php?products_id=100

The changes to the original binary can be easily reviewed by comparing the original application to this version using the HxD utility.<br>
HxD - https://mh-nexus.de/en/hxd/

## Additional Observations
1. Because I manually edited the original .exe binary, you will need to explicitly tell Windows it's allowed to run this hand-patched executable. This needs to be done just once. It's that blue "Don't run" pop-up you'll get after extracting the file from the .zip and running. From there, you can click on the "More info" link, then give Windows permission to run the file. Wish I knew how to fix that!

2. If you use this modified utility to write settings to either a file or directly to the device which normally would have been disallowed by the original configurator but then use the original configurator to read the configuration from the device or file, the settings will be retrieved but cannot be written back to either the device or a file. This is, of course, because those relaxed settings will be out of range according to the original configurator.

3. It seems the author's original configurator has not been updated since 2017 according to the file date in the original .zip file. The original v1.13 configurator program has a bug where the Telemetry reports and Weather reports beacon settings indicate beacons in the range of (5 - 1440) minutes are allowed. However, the user interface only allows 3 digits to be entered into those fields! So the maximum minutes that can be entered is 999. (If I can find the location in the executable that controls that, I hope this could be an easy fix too. ;-)

<b>Disclaimer: As expected, all procedures above performed at your own risk.</b>
