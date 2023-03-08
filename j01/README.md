# case INSENSITIVITY

A few years ago I corrupted my macOS install. In order to rectify it I had no
choice but to reformat my harddrive. This is simple enough to do on a mac. You
hold `⌘-R` during startup which brings you into the recovery menu. You walk
through some steps and then you are given a setting for the drive meekly titled
"format."

![An apple menu showing 4 options: APFS, APFS (Encrypted), APFS
(Case-sensitive), and APFS (Case-sensitive, Encrypted)](./formatoptions.png)

I have a background in Linux, which typically has case sensitive file systems by
default, so I elected to go with the "APFS (Case-sensitive, Encrypted)" option.
Little did I know at the time, I made a **grave and unrecoverable** error that
would punish me years down the line.

Fast forward to the present. For my CSCI-431W class at Chico State, I was
instructed to install Adobe XD. I assumed this would be fairly trivial, so like
the good college student that I am I waited until the last minute to do so. At
around 9:30 AM I go to the Adobe XD website, download it, open the installer,
only to be greeted with this:

![An adobe creative cloud error message saying case-sensitive volumes are not
supported.](./adobeerror.png)

This error message from Adobe is completely useless. A good error message should
be **easily recoverable**, but outside of the hint that I should "choose a
different volume," this error screen gives me nothing to go off of. But here's
the thing: *I didn't even choose a volume!* There wasn't even an option to
*pick* a volume.

At this point I'm pretty lost so I decide to search the internet for the error.
I finally discover the full ramifications of my actions years prior: it is
**impossible** to install Adobe products if you have formatted your macOS
install volume to be case-sensitive. Furthermore, it is impossible to convert a
case-sensitive drive to a case-insentive one without losing all of your data.

Luckily, I don't store any useful data on my laptop, so at about 9:45 I promptly
make the decision to reformat my laptop. I've done it before, so I meander through
the "`⌘-R` -> delete partition -> blah blah blah" procedure I vaguely remember.
But I messed up. I deleted my main partition and then rebooted, inadvertantly
deleting the recovery image built into macOS as well.

![A screenshot of the image you get when you boot up a macbook without an
operating system.](./questionmark.png)

Luckily Apple engineers have added a failsafe for this exact situation. It is
still possible to recover from this error without much effort, or at least so I
thought. You can do an "internet recovery" which downloads the required files
to repair your operating system after you connect to a wifi network. By holding
`⌘-Shift-R` I accessed this menu, then tried connecting to the `csuchico`
network. I then tried the `csuchico-guest` network. It also failed. Finally I
connected my phone's wireless hotspot to my computer (I have unlimited data) and
that worked. At this point it's about 10:20. I wait for the download for the
next 20 minutes, and right after the progress bar reaches the end, it errored out.

At this point I had to leave for my next class which is directly before my 431W
class, so I simply accepted my fate that I would not be able to use Adobe XD if
required in class that day. Fortunately, I didn't need it until the next week,
but I now had a pressing problem at hand.

When I arrived back at home for the day I tried again to recover from the
network using my home wifi, believing the error to be related to a poor
connection over my hotspot. Once again, it gave an enigmatic error with no
explanation. I migrate to a backup plan of recovering from a USB drive connected
to my laptop. I enlist the help of my roommate's laptop to format my USB drive
then plug it in. More waiting. This also doesn't work.

I now became worried that I had somehow permanantly bricked my laptop. I spend
about an hour researching this particular issue and find out that since my
laptop is a newer model with the T2 security chip, it is not possible to do a
normal internet or USB recovery. You must do the additional step of "restoring"
your mac by resetting the firmware in the T2 chip. The only way to do this is by
installing the special "Apple Configurator Software" and
then connecting two macs together using specific USB ports on each device.

![A screenshot of the apple configurator app with a context menu showing the
"revive device" option selected.](./restore.png)

Apple's current system is flawed because it gives the user no insight into the
current status of the system. There is no way to tell if your mac has a T2 chip
and it is preventing you from reinstalling your operating system. You must
simply guess that that is the case and hope that you have access to another mac
to test your hypothesis.

A few years ago I made the decision to format my drive using a case-sensitive
file system. This is not a decision that I, or anyone would ever make if they
were aware of the full ramifiactions it entailed. If Apple's interface better
communicated that formatting my drive with a case-sensitive file system would
prevent me from installing some of the most popular software on the planet, I
would not have elected to pick that option. Further, their recovery flow for
macbooks with T2 chips is very poorly designed and gives the user no insight
into what is preventing you from recovering their mac.

