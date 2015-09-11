# Android Glossary #

**Android OS** - Like Windows Mobile but based on Linux, using a Java based front end.

**Linux** - Open Source operating system used instead of Windows XP/Vista, Mac OSX etc... it's free (as in beer).

**Open Source** (<a href='http://en.wikipedia.org/wiki/Free_and_open_source_software'>From Wiki</a>_) – Free and open source software, also F/OSS, FOSS, or FLOSS (free/libre/open source software) is software which is liberally licensed to grant the right of users to study, change, and improve its design through the availability of its source code._

**Root** (_as in access_)- root is like the administrator account on a windows machine (also referred to as su, or superuser). It allows you to have complete access to the underlying OS of a linux or **nix based machine. For the G1, it allows for the use of themes, native backup functionality, manually selecting which apps can utilize root access, auto-rotate screen, multi-touch in browser, moving applications/caches to the sd card etc...**

**Root** (_as in location_)- the 'root' of a folder or drive is the top most area of that location. In windows, C:\ is the 'root' of your hard drive. The 'root' of your SD card just means you haven't moved into any subfolders.

**Shell** – (_also heard as terminal, bash, command line_) This is a loose definition, but it’s basically a command line to run specific actions against the OS.

**Bootloader** – the SPL and IPL of a flash based device. See description <a href='http://code.google.com/p/android-roms/wiki/SPL'>here</a>.

**SPL** (_Secondary Program Loader_) - You get to the SPL by holding the '**camera**' button while powering on your phone. This is where you flash NBH images. See bootloader above.

**Recovery Mode** - Holding the '**Home**' key while while powering on the G1 will take you into Recovery Mode. From here you can perform a NANDroid backup, wipe your phone, access a command line and of course, flash your phone with an _update.zip_ file.

**RC##** (_or release candidate_) – In context to the G1, it is an official release of Android from T-Mobile meant specifically for the G1 (not ADP).

**ADP** (_Android Developer Phone_) – A Google specific (or carrier non-specific) version of the G1/Dream that has root access by default and is meant for developers writing apps for the G1, or Android in general.

**ADP vs. RC##** - Neither RC’s or ADP versions are tied to their respective hardware. With the right bootloader, you can flash an ADP image to a G1 or an RC image to an ADP.

**JFV1.##** - Is a specific Version of a JesusFreke ROM. JesusFreke is a developer on the <a href='http://xda-developers.com'>xda-developers website</a> that has graciously spent his time to modify the G1 OS to allow us to have root access to our phones. This gives us the ability to explore and modify our phones via a command line.

**Cupcake** – a development branch of the Android OS that contains many improvements that was merged into the master build of Android and is currently being released to new phones as Android 1.5.

**Nandroid** – a utility, accessible through Recovery Mode, that allows you to backup your phone and restore to the exact condition at backup.

**Apps2SD** – Applications moved to your SD card instead of internal memory. Some people like the extra room, some people don’t want to hassle with the partitioning.

**Partition** – just like the partitions that separate cubicles in an office, a partition separates parts of a drive.

**File system** – there are many. It’s basically a specific way of organizing data on a partition. FAT(32) is generally windows, ext2 is generally linux. This is not a hard and fast rule, just most common in context with what you’ll see here.

**Scripts** – scripts are text files that contain a list of commands to perform. Instead of typing each command out multiple times, a script can be run that will initiate all steps listed in the script.

**Android SDK** (_System Developer’s Kit_) – This includes all tools (sans fastboot) that a developer needs to create applications for the G1. It also has tools for interacting with the phone via a command line (ADB).

**ADB** - is a part of the SDK that allows you to run commands against the G1 in lieu of using the terminal on the phone itself.

**Fastboot** - is a tool used to flash system images (.img files) to the G1 from a command line on your pc. IMG files are created when you do NANDroid backups and official images can be downloaded from HTC as well. To get to fastboot mode on your phone, hold the back button while powering on.