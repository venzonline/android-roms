<font color='#FF0000'>=================================================================================</font><br>
<blockquote><font color='#FF0000'>DISCLAIMER: I AM NOT RESPONSIBLE IF YOU BRICK / RUIN YOUR PHONE IN ANY WAY.</font>    <br>
<font color='#FF0000'>BASIC COMPUTER SKILLS REQUIRED</font>                                                 <br>
<font color='#FF0000'>IF YOU DO NOT KNOW WHAT ROOT IS ... YOU PROBABLY DON'T NEED IT</font>                 <br>
<font color='#FF0000'>=================================================================================</font><br></blockquote>


<b>PROCEED WITH CAUTION</b>

<h1>Setting up your phone to work with Apps 2 SD (A2SD)</h1>

The SDcard will need two partitions, the first Fat / Fat32 & the second Ext2<br>
<i>For the Ext2 partition I wouldn't go higher than 1.5GB cuz you may run into some issues.  I was staying around the 500MB / 750MB area & it was working nice.  As all the guides I've read state not to exceed the 1.5GB Marker.</i>

After you have both partitions setup you can install the OS, then it's just a matter of setting up the symlinks & moving the apps over / installing new ones.<br>
Now remember it may be best to do a wipe prior to installing this build if you aren't already on the same A2SD Build already.<br>
<br>
Once the OS is installed first thing I would do is from a terminal on the phone / ADB Shell:<br>
<br>
<font color='#FF0000'>su</font><br>
<font color='#FF0000'>busybox df -h</font>

If you don't see a row that has <i>/system/sd</i> on it then the process didn't pick up your SDCard.  I'd suggest you to re-install / re-format the card.<br>
<br>
Next if you didn't perform a wipe we'll move the data over, run these cmds either via terminal / adb shell:<br>
<br>
<font color='#FF0000'>busybox cp -a /data/app /system/sd/</font><br>
<font color='#FF0000'>busybox cp -a /data/dalvik-cache /system/sd/  (optional)</font><br>
<font color='#FF0000'>busybox cp -a /data/data /system/sd/  (optional)</font><br>

The last two cmds here are optional (they are to move the cache for each app) & some have reported issues when copying these over so if you are having issues I would leave these on the /data partition.<br>
<br>
1 Once your done with the above, power off your phone<br>
2 Press & hold the Home Button & press Power to boot into Recovery Mode<br>
3 Once the recovery menu opens & it's showing you JF's custom menu press <b>ALT+X</b> to enter the Recovery Terminal.<br>
4 Press enter & a prompt should come up with a "#".<br>

Next enter these cmds:<br>
<br>
<font color='#FF0000'>mount data</font><br>
<font color='#FF0000'>rm -rf /data/app</font><br>
<font color='#FF0000'>ln -s /system/sd/app /data/app</font><br>
<font color='#FF0000'>rm -rf /data/data  (optional)</font><br>
<font color='#FF0000'>ln -s /system/sd/data /data/data  (optional)</font><br>
<font color='#FF0000'>rm -rf /data/dalvik-cache  (optional)</font><br>
<font color='#FF0000'>ln -s /system/sd/dalvik-cache /data/dalvik-cache  (optional)</font><br>
<font color='#FF0000'>reboot</font><br>

Again the 4-7 cmds are optional & for the cache only of an app, so if you moved the cache over in the above cmds then on this section you will run them as well.<br>
<br>
<b>You must run the optional cmds in both sections for them to work, or run them in neither!</b>

During the reboot process your phone might take a while at the android screen since it has to populate the apps tray. If it lasts >5-10 minutes then something likely went wrong. Make sure you did all the steps correctly & if you did try the steps in the recovery terminal section of this tutorial again. If it still doesn't work, post here & we'll try to get it sorted out. That aside, enjoy having your apps on SD card!<br>
<br>
<i>Also I wouldn't suggest you moving the /data/app-private.</i>

<b>To Continue on please go to</b><a href='http://code.google.com/p/android-roms/wiki/Unroot'>Unroot your Phone / Place Phone Back to Stock</a>