<font color='#FF0000'>=================================================================================</font><br>
<blockquote><font color='#FF0000'>DISCLAIMER: I AM NOT RESPONSIBLE IF YOU BRICK / RUIN YOUR PHONE IN ANY WAY.</font>    <br>
<font color='#FF0000'>BASIC COMPUTER SKILLS REQUIRED</font>                                                 <br>
<font color='#FF0000'>IF YOU DO NOT KNOW WHAT ROOT IS ... YOU PROBABLY DON'T NEED IT</font>                 <br>
<font color='#FF0000'>=================================================================================</font><br></blockquote>


<b>PROCEED WITH CAUTION</b>

<h1>- Restore Phone Via NANDROID Backup & Fastboot -</h1>

So now you've just backed up your phone or bricked it and want to know how in the hell do I recover my phone with these backups I'm creating... <br>

<b>Things you will need:</b><br>
<b>Android SDK</b>: <a href='http://developer.android.com/sdk/download.html?v=android-sdk-windows-1.5_r1.zip'>http://developer.android.com/sdk/download.html?v=android-sdk-windows-1.5_r1.zip</a><br>
<b>Fastboot Windows Binary</b>: <a href='http://android-roms.googlecode.com/files/fastboot-win32.zip'>http://android-roms.googlecode.com/files/fastboot-win32.zip</a><br>
<b>Android USB Drivers</b>: <a href='http://android-roms.googlecode.com/files/android_usb_windows.zip'>http://android-roms.googlecode.com/files/android_usb_windows.zip</a> <br>

<b>Installing the SDK</b> (<a href='http://developer.android.com/sdk/1.5_r1/installing.html):'>http://developer.android.com/sdk/1.5_r1/installing.html):</a>
Download the Android SDK (link above) extract the files to a location on your PC i.e. C:\sdk<br>
Next On Windows, right-click on My Computer, & select Properties. Under the Advanced tab, hit the Environment Variables button, & in the dialog that comes up, double-click on Path (under System Variables). Add the full path to the tools/ directory to the path.<br>
<blockquote>So using the example from above the path you would be adding is c:\sdk\tools</blockquote>

<i>- Note that, if you update your SDK in the future, you should remember to update your PATH settings to point to the new location, if different. -</i>

-Once the SDK is extracted & the Environment Variables updated<br>
-Download the Fastboot Windows Binary & extract it in the same folder as adb. So using the same example you will place the files in the c:\sdk\tools<br>
-Reboot your phone<br>
-Turn your phone on & hold both <b>Camera + Power</b><br>
-You should now see a white screen with three androids on skateboards (If you do not see this STOP, repeat the Hard SPL Installation above)<br>
-Take out the usb cable & connect it to your phone, now press the back key on the phone.<br>
-In the middle of the screen your phone should now say <font color='#FF0000'>FASTBOOT</font>, if it says SERIAL keep pressing back on the phone till you see <font color='#FF0000'>FASTBOOT</font><br>
-If it asks you to install drivers, then use the usb drivers above.<br>
<br>
<br>
<hr><br>
<br>
<br>
-If it doesn't ask you to install a driver, you need to figure out if the correct driver is loaded already.<br>
-Right click on My Computer, & click Manage, then go to the device manager<br>
-If you see an "<i>ADB Interface</i>" category at/near the top, with "<i>HTC Dream</i>" under it, then you're good to go. Fastboot should be working for you.<br>
-If you don't see an "<i>ADB Interface</i>" category, then it's likely that windows loaded the USB Mass Storage driver for it automatically.<br>
-In the device manager, go down to "Universal Serial Bus Controllers", & see if you have at least one "<i>USB Mass Storage device</i>". If you have multiple ones, you'll need to go through each to find the correct one.<br>
-To find the correct one, right click on the USB Mass Storage device & click Properties.<br>
-Go to the Details tab.<br>
-In the combo box at the top that says "<i>Device Instance Id</i>", bring up the pull down & choose "<i>Compatible Ids</i>".<br>
-If that is the correct device, then you will see 3 entries:<br>
<ul><li>USB\Class_ff&SubClass_42&Prot_03<br>
</li><li>USB\Class_ff&SubClass_42<br>
</li><li>USB\Class_ff</li></ul>

Once you find the correct device, go to the driver tab, & click "<i>Update Driver</i>". Choose "<i>No, not this time</i>", then "<i>Install from a list or specific location</i>", then "<i>Don't search, I will choose the driver to install</i>", & then choose the same usb driver that you used to get adb to work.<br>
<br>
-Once you have completed this Open a Cmd Prompt (<b>Windows Key + R</b>, then cmd)<br>
-fastboot devices<br>
It should list a device in the list, if it does you are fine to flash images to your phone if not please repeat the process above. You may have to delete the android phone under the device manager.<br>

From the NANDROID Backup you will only need to flash three files:<br>
-<b>data.img</b><br>
-<b>system.img</b><br>
-<b>boot.img</b><br>

Copy the above three files to the directory on your Cmd Prompt or change directories through the Cmd Prompt to the location of the nandroid files either way will work.<br>
<br>
Once the files are in the same directory that Cmd Prompt is accessing then type each cmd below followed by enter. The cmd will send & then flash the image.<br>
<br>
<font color='#FF0000'>fastboot flash boot boot.img</font><br>
<font color='#FF0000'>fastboot flash system system.img</font><br>
<font color='#FF0000'>fastboot flash userdata data.img</font><br>
<font color='#FF0000'>fastboot reboot</font>
<br>

<b>Your phone will reboot into the OS & your back to the image you just flashed! ENJOY!</b>

<br>
Finally if you want to return your phone back to Stock please continue on...<br>
<br>
<b>To Continue on please go to</b><a href='http://code.google.com/p/android-roms/wiki/Fat_Ext2_Partition'>Partition your SDCard Fat32 / Ext2</a>