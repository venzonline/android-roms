<font color='#FF0000'>=================================================================================</font><br>
<blockquote><font color='#FF0000'>DISCLAIMER: I AM NOT RESPONSIBLE IF YOU BRICK / RUIN YOUR PHONE IN ANY WAY.</font>    <br>
<font color='#FF0000'>BASIC COMPUTER SKILLS REQUIRED</font>                                                 <br>
<font color='#FF0000'>IF YOU DO NOT KNOW WHAT ROOT IS ... YOU PROBABLY DON'T NEED IT</font>                 <br>
<font color='#FF0000'>=================================================================================</font><br></blockquote>


<b>PROCEED WITH CAUTION</b>

<h1>Rooting your Phone</h1>

<b><i>- On RC29 phones and lower, anything you type into your keyboard is also being run in a hidden console with root permissions. -</i></b>

To get root access, do the following:<br>
<br>
1 Download <i>recovery.img</i> and copy it to your SD card (see the previous instructions on how to copy from your computer to your Phone's SD card). Confirm file is named "<i>recovery.img</i>"<br>
<blockquote>Location of the recovery.img: <a href='http://android-roms.googlecode.com/files/recovery.img'>http://android-roms.googlecode.com/files/recovery.img</a>
2 Download the Hard SPL and copy the zip file to the SD card. Rename this file to "<i>update.zip</i>".<br>
Location of the Hard SPL: <a href='http://android-roms.googlecode.com/files/splhard1_update_signed.zip'>http://android-roms.googlecode.com/files/splhard1_update_signed.zip</a>
3 Make sure both files are on the root of your SD card.<br>
4 Restart your phone normally and wait for your phone to start up fully and show the home screen.<br>
5 After your phone starts up, hit the enter key twice, type "telnetd" and press enter. (Yes, it will start up a contact search, don't worry. Just type it.)(Also if you have terminal installed you can enter this cmd on the terminal screen)<br>
6 Turn on your WiFi Radio and connect to your Wireless Network, once connected ... Download and install an Application from the Market "Telnet" and connect to localhost.<br>
7 If you connect successfully, you will have a root prompt "#". <br>
8 Type the following into Telnet (these commands will give you root access easier in the future):<br></blockquote>

(The below process changes the /system partition from read only to read/write)<br>
<blockquote><i>mount -o rw,remount -t yaffs2 /dev/block/mtdblock3 /system</i><br>
<i>cd /sdcard</i><br>
<i>flash_image recovery recovery.img</i><br>
<i>cat recovery.img > /system/recovery.img</i><br></blockquote>

<b><i>- You now have root -</i></b>

<b>To Continue on please go to</b><a href='http://code.google.com/p/android-roms/wiki/Install_Hard_SPL'>Installing the Hard SPL</a>