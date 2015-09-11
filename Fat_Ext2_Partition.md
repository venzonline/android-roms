<font color='#FF0000'>=================================================================================</font><br>
<blockquote><font color='#FF0000'>DISCLAIMER: I AM NOT RESPONSIBLE IF YOU BRICK / RUIN YOUR PHONE IN ANY WAY.</font>    <br>
<font color='#FF0000'>BASIC COMPUTER SKILLS REQUIRED</font>                                                 <br>
<font color='#FF0000'>IF YOU DO NOT KNOW WHAT ROOT IS ... YOU PROBABLY DON'T NEED IT</font>                 <br>
<font color='#FF0000'>=================================================================================</font><br></blockquote>


<b>PROCEED WITH CAUTION</b>

<h1>SDSPLIT repartition your SDcard Fat32 / Ext2</h1>

1 Must have a Custom ROM installed!<br>
2 Install the sdsplit executable to your phone. To so this, open the '<i>terminal</i>' application / ADB Shell and type the following commands at the prompts:<br><br>
<b><i>(Note: you will need an internet connection on your phone for this step)</i></b><br>
<i>If you are running these cmds from ADB Shell you do not need to type "su" as you will already have root</i>

<font color='#FF0000'>$ su</font> <br>
<font color='#FF0000'># cd /data</font> <br>
<font color='#FF0000'># wget <a href='http://64.105.21.209/bin/lib/droid/sdsplit'>http://64.105.21.209/bin/lib/droid/sdsplit</a></font> <br>
<font color='#FF0000'># chmod 555 sdsplit</font> <br>
<font color='#FF0000'># exit</font><br>

3 Decide the size of your FAT partition:<br>
<br>
You should use one of two approaches to decide the size of your FAT partition. The first one involves simply directly deciding this size (i.e. I want a 5G FAT partition). In this case, the EXT2 partition will be the remainder of the card.<br>
<br>
<b>size_of_fat_partition = size</b>

The second method is based upon the fact that you want to decide the size of the EXT2 partition and would like the FAT partition to be the remainder of the card. In this case, the size of the FAT partition will be based on the size of your sdcard and the size of the EXT2 partition that you want. Use this formula to calculate it:<br>
<br>
<b>size_of_sdcard - size_of_ext2_partition = size</b>

So, if you have an <b>8GB</b> sdcard and want <b>1GB</b> of space for apps on your EXT2 partition, use <b><i>7000M</i></b> for the FAT size.<br>
<br>
No matter which method you use, you will need to specify either bytes (no parameter), kilobytes (K) or megabytes (M) . So, for a <i>5G</i> partition would use a <i>5000M</i> size parameter.<br>
<br>
<b>Note: The size parameter is currently <i>case</i> <i>sensitive</i>, use 7500</b><font color='#FF0000'>M</font>, not 7500<font color='#FF0000'>m</font>!<br>
<br>
<br>
4 Backup your SDCard onto your PC <br>

<i>Note: To figure out how much data (in K) you have on you FAT partition, you can type the following in your terminal / ADB Shell (the sdcard can not be mounted for this cmd to work):</i>

<font color='#FF0000'>$ du -s /sdcard</font>

<i>Note: to find out how much free space is left on your /data partition type (see available)</i>

<font color='#FF0000'>$ df /data</font>

5 Run sdsplit. Use the size from step 3 below (do not forget the "<b>M</b>" in size if you are specifying megabytes):<br>
<i>(Note: you will need an internet connection on your phone for this step)</i>


<b>Note: If you are using the JF1.5 update, you should put a <i>-nc</i> at the end of the commands below since system configuration is not needed!</b>

<b>Non JF1.5 Build:</b><br>
<font color='#FF0000'>$ su</font><br>
<font color='#FF0000'># /data/sdsplit -nd -fs size</font><br>
<font color='#FF0000'># exit</font><br>

<b>JF1.5 Build:</b><br>
<font color='#FF0000'>$ su</font><br>
<font color='#FF0000'># /data/sdsplit -nd -fs size -nc</font><br>
<font color='#FF0000'># exit</font><br>

Please, remember to record the output of this stage if you run into a problem. There will be a permanent record of it in, <i>/data/sdsplit.log</i>.<br>
<br>
6 Reboot your phone, via terminal:<br>
<font color='#FF0000'>reboot</font><br>

Via ADB Shell:<br>
<font color='#FF0000'>adb shell reboot</font><br>

7 Restore your data from your PC to your Fat partition of your SDCard.<br>

8 <b>You're done! You should have two partitions now on your sdcard. The FAT one mounted at /sdcard and the EXT2 one mounted at /system/sd.</b>

<br>
<br>
<hr><br>
<br>
<br>
<br>
<b>DO IT AGAIN:</b>

If you simply want to change the size of your partitions because you are not happy with them after the first run, and you have not wiped or reinstalled your system in the mean time, repeat step 5 with the <b><i>-fu</i></b> and <b><i>-nc</i></b> options at the end. <i>Be aware that this will delete any data you have put on the EXT2 partition</i>. You may do this as many times as you like.<br>

/data/sdsplit -nd -fs size <b>-fu -nc</b><br>

i.e. <br><br>
<font color='#FF0000'>$ su</font><br>
<font color='#FF0000'># /data/sdsplit -nd -fs 7000M <b>-fu -nc</b></font><br>
<font color='#FF0000'># exit</font><br>

<br>
<br>
<hr><br>
<br>
<br>
<b>Problem Report:</b>

If your run into any serious problems, there is a log file located at: <i>/data/sdsplit.log</i> if you can get it off your phone.<br>
<br>
<b>To Continue on please go to</b><a href='http://code.google.com/p/android-roms/wiki/A2SD'>Setting up your phone to work with Apps 2 SD (symlinks)</a>