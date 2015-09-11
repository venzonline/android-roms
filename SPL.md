<font color='#FF0000'>=================================================================================</font><br>
<blockquote><font color='#FF0000'>DISCLAIMER: I AM NOT RESPONSIBLE IF YOU BRICK / RUIN YOUR PHONE IN ANY WAY.</font>    <br>
<font color='#FF0000'>BASIC COMPUTER SKILLS REQUIRED</font>                                                 <br>
<font color='#FF0000'>IF YOU DO NOT KNOW WHAT ROOT IS ... YOU PROBABLY DON'T NEED IT</font>                 <br>
<font color='#FF0000'>=================================================================================</font><br></blockquote>




<b>PROCEED WITH CAUTION</b>
<br>
<h1>About SPLs</h1>

This page contains information about SPLs for the HTC Dream (aka T-Mobile G1 and ADP1). What is a SPL? The SPL, or Second Program Loader, in conjunction with the IPL comprise a device's bootloader. Aside from bootstrapping Android, the bootloader also fulfills various diagnostic functions. One of these functions is the manipulation of data in the device's internal flash ram. Depending on the SPL installed, the user can apply a signed NBH file, flash nand images, and more. Note that the SPL is installed and operates independently of the Android build that runs atop it.<br>
<br>
Currently there are three SPLs available. The G1 variant is the SPL that is installed in stock T-Mobile G1 phones. The Engineering variant is found in the Android Dev Phone 1. Finally, the HardSPL is a modification of the Engineering variant by cmonex, with additional hacker-friendly functionality. HardSPL is the recommended SPL.<br>
<br>
<h1>Installation</h1>

The SPLs are packaged in the familiar <i>update.zip</i> format and install from the recovery console in the same fashion as other update files:<br>
<br>
<ul><li>1. If you are installing onto a G1, your G1 must have a modified recovery partition. If you have one of JesusFreke's Android builds installed, then you have a modified recovery partition<br>
</li><li>2. Download the desired SPL zip file (<a href='http://code.google.com/p/android-roms/downloads/list?q=label:SPL'>SPL Downloads</a>), rename it to <i>update.zip</i> and copy it to the root of your sdcard. As usual, remember to use a USB cable with a ferrite core and dismount your USB drive before disconnecting.<br>
</li><li>3. Reboot the phone into recovery console and flash the update with <b>ALT+S</b>.<br>
</li><li>4. To confirm it has installed properly, power on the G1 with <font color='#FF0000'>END</font> + Camera<b>to enter the bootloader. When you are done, press</b><font color='#00FF00'>CALL</font> + MENU + <font color='#FF0000'>END</font><b>to leave the bootloader.<br>
</li><li>5. To revert a G1 to its factory original SPL, simply use the G1 Original SPL.</li></ul></b>

<h1>HardSPL (recommended)</h1>

<b>VER: HSPL10.95.3000</b><br>
ZIP: splhard1_update_signed.zip<br>
MD5: 6502af25b9e9fbe1322cc405559af1ca<br>
SHA1: 59485b21f69acb6e9f70a4cd5ff4aefea722fc50<br>

HardSPL is a modification of the Engineering SPL by cmonex. In addition to the functionality of the Engineering SPL, HardSPL also allows NBH files to be used without matching the CID (carrier ID) check. At the current time the main benefit of this is to allow European G1s flash American NBH files and vice versa. All other features and attributes of the Engineering SPL (such as the ability to flash the mtds from nand backup images) are present. Using the Nandroid backup scripts to create nand backups for this purpose is recommended.<br>
<br>
<h1>Engineering SPL</h1>

<b>VER: HBOOT-0.95.3000</b><br>
ZIP: EngBootloader_v2_NoSigCheck.zip<br>
MD5: 8008e01cb2c35e06b704e4dfb624ce4e<br>
SHA1: d94f087b9eed8f59bc90d84c290ce475dbee07f9<br>

The Engineering SPL is a custom SPL installed in devices intended for Android development. It has existed since before the launch of the G1 and is now available to the general public as preinstalled on the Android Dev Phone 1, the official development device sold by Brightstar Corp. This SPL, in addition to flashing signed NBH files, can also flash nand dumps through the use of the fastboot protocol (as defined in the legacy bootloader documentation). This is a convenient way to flash the mtd partitions and can be greatly useful in the event that an undesirable build of Android is advertently or inadvertently installed.<br>
<br>
This SPL was first originally dumped from a G1 which dream_kill received as a replacement from T-Mobile by cmonex and JesusFreke. The file was released by Disconnect on his <a href='http://www.gotontheinter.net/'>webpage</a>.<br>
<br>
<h1>G1 Original SPL</h1>

<b>VER: HBOOT-0.95.0000</b><br>
ZIP: G1OrigBootloader_nocheck.zip<br>
MD5: ae58b427b797707c453f3b3fa9d13c76<br>
SHA1: aac5b75c348ee33c29aa24612d23a5e626a8c075<br>

This is the original SPL which is installed in a stock G1. It is easily distinguished by the "trademark" red-green-blue bootloader screen which appears in many HTC phones. This SPL does not support the fastboot protocol and thus will not allow the user to flash nand backup images.<br>
<br>
Before the leak of the TC4-RC29 and TC5-RC7 signed NBH images, users running stock RC30 and RC8 were unable to downgrade and install modified Android builds. On January 1st, 2008, xda-dev user chavonbravo leaked the aforementioned files, which allowed users to downgrade G1s through the original SPL. This SPL was dumped by damien667.