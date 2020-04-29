---
title: "Solaris installation"
date: 2020-04-27T127:43:00+01:00
output:
  blogdown::html_page:
    toc: true
---

## Introduction

We use Solaris in VMware ESXi. It also works in other VMware
products, e.g. VMware Fusion, and it also seems to work in
VirtualBox.

This is an installation walkthrough in VMware Fusion.

We use Solaris 10, because that's what CRAN uses. Solaris 11
is probably similar.

## Base OS

1. Download the Solaris 10 ISO from
https://www.oracle.com/solaris/solaris10/downloads/solaris10-get-jsp-downloads.html

2. Then add a new virtual machine.

3. Select "image" and use the downloaded image.

{{< figure src="choose-media.png" >}}

{{< figure src="iso.png" >}}

4. You probably want to customize the defaults, and have a
bigger disk.

{{< figure src="default.png" >}}

5. For that you need to save the VM first.

{{< figure src="default-save.png" >}}

6. Choose "Hard Disk"

{{< figure src="settings.png" >}}

7. Choose the size tha suits you

{{< figure src="disk-size.png" >}}

8. You might want to change the memory size and number of
processors.

{{< figure src="cpu-memory.png" >}}

9. We are ready to go

{{< figure src="ready-to-go.png" >}}

10. The default is fine

{{< figure src="boot-menu.png" >}}

11. Here we use the interacive GUI installer (1).

{{< figure src="install-menu.png" >}}

12. Keyboard

{{< figure src="keyboard.png" >}}

13. Ready to start the GUI

{{< figure src="before-gui.png" >}}

14. GUI starting up

{{< figure src="gui-start.png" >}}

15. Select installer language

{{< figure src="install-lang.png" >}}

16. Welcome to the GUI installer

{{< figure src="welcome-gui.png" >}}

17. Network we need, yes

{{< figure src="network.png" >}}

18. We want DHCP, the host will provide it.

{{< figure src="dhcp.png" >}}

19. We might as well allow IPv6.

{{< figure src="ipv6.png" >}}

20. We don't need Kerberos.

{{< figure src="kerberos.png" >}}

21. We don' need DNS or other name service, either.

{{< figure src="dns.png" >}}

22. We don't need NFSv4, so the default is fine for this.

{{< figure src="nfsv4.png" >}}

23. Select the time zone as you wish.

{{< figure src="timezone1.png" >}}

{{< figure src="timezone2.png" >}}

24. Make sure the time is correct.

{{< figure src="datetime.png" >}}

25. Set the root password.

{{< figure src="rootpw.png" >}}

26. You don't actually need to enable remote services to
have ssh.

{{< figure src="enablessh.png" >}}

27. You can register to Oracle if you want.

{{< figure src="oracle.png" >}}

28. No need for any proxies

{{< figure src="proxy.png" >}}

29. Network setup summary

{{< figure src="net-summary.png" >}}

30. Yet another welcome screen

{{< figure src="welcomex.png" >}}

31. Installer options

{{< figure src="installer-options.png" >}}

32. Eject the DVD via VMware if the reboot does 
not start the installed system.

{{< figure src="eject-cd.png" >}}

33. Install media is the DVD.

{{< figure src="install-media.png" >}}

34. Accept the license

{{< figure src="accept-license.png" >}}

35. We'll do a custom install.

{{< figure src="custom-install.png" >}}

36. Select installed locales.

{{< figure src="locales.png" >}}

37. Select default locale.

{{< figure src="default-locale.png" >}}

38. No additional products.

{{< figure src="additional-product.png" >}}

39. We can install the entire product.

{{< figure src="install-all.png" >}}

40. Select disk to install on.

{{< figure src="select-disk.png" >}}

{{< figure src="select-disk2.png" >}}

41. Customize disk partitions

{{< figure src="fdisk.png" >}}

42. Instead of the default partitions on the first picture we
are better off with the ones on the second, because it is
simpler to manage a single partition, instead of the old-school
server setup.

{{< figure src="fdisk2.png" >}}

{{< figure src="fdisk3.png" >}}

43. Ready to install

{{< figure src="ready-to-install.png" >}}

{{< figure src="installing.png" >}}

44. Rebooting after install

{{< figure src="rebooting.png" >}}

45. Console login. Do not log in here, wait for the graphical
login screen.

{{< figure src="console-login.png" >}}

46. GUI login. Log in as the `root` user. Select the Java
Desktop GUI after login. Or select it in the Options menu before
logging in.

{{< figure src="gui-login.png" >}}

47. TADA!

{{< figure src="after-login.png" >}}

48. Open a terminal

{{< figure src="terminal.png" >}}

49. Test the network connection

{{< figure src="test-net.png" >}}

50. Install OpenCSW

{{< figure src="opencsw.png" >}}

{{< figure src="opencsw2.png" >}}

## Setup ssh

51. Add a regular user

{{< figure src="add-user.png" >}}

52. Check our IP address

You can use this IP address (192.168.49.128 on the picture)
to ssh into the Solaris box, using the newly created user.
(The default ssh server configuration does not allow ssh logins
for the root user.)

In VMware Fusion ssh works automatically. In VirtualBox you
might need to use port forwarding. On ESXi you need to set up
a port forward in the firewall.

{{< figure src="my-ip.png" >}}

## Set up `sudo`

This lets you log in as a regular user and still run configuration tasks.
OpenCSW has sudo:

```sh
pkgutil -y -i sudo
echo 'rhub ALL=(ALL) NOPASSWD: ALL' >/etc/opt/csw/sudoers.d/rhub
```

## Install Oracle Developer Studio

53. You need to download Oracle Developer Studio (ODS), even if you only
want to use GCC from OpenCSW. The reason for this is that ODS comes with
a number of patches, and without these patches GCC does not work properly.
Namely, g++ is not a proper C++11 compiler if they are not installed.
If you are sure that you don't need ODS, then just install the patches,
either by calling the `install_patches.sh` shell script directly, or from
the graphical installer and then cancel the installation.

Once ssh works, you can copy a downloaded tarball of
Oracle Developer Studio to the machine. First download it
on the host machine. I.e. not inside the installed Solaris box,
because default Solaris installation does not have any
browser with a strong enough encryption for the HTTPS download
from Oracle.

You can download it at
https://www.oracle.com/tools/developerstudio/downloads/developer-studio-jsp.html
You need the SVR4 installer on x86.

Then copy this to the machine.

{{< figure src="copy-ods.png" >}}

54. Then install ODS on the guest

{{< figure src="ods1.png" >}}

55. You'll need to install some patches first, but the installer
can do that for you. Choose "More Info" and then "Execute
install_patxches.sh now". Do not worry about the incompatible
Java version, that is about the GUI developer tools, which we
won't use. (Or you can update Java later.)

To check that the patches are properly installed, call this from a
terminal: `showrev -p | less`. My version of ODS came with six patches,
and these five were installed: 119967-02, 120754-17, 119964-35,
152227-01, 152229-01. Check that they are installed.

{{< figure src="ods2.png" >}}

{{< figure src="ods-patches.png" >}}

56. Once the patches have been applied, the installer is
ready to go.

{{< figure src="ods-inst.png" >}}

57. First you need to select the installation location.
`/opt` is as good as any. Do **not** create symlinks in
`/usr/bin`, as we try to avoid mixing the GNU compilers
from OpenCSW and the ODS compilers

{{< figure src="ods-location.png" >}}

58. One last summary.

{{< figure src="ods-start-install.png" >}}

59. Installing happily.

{{< figure src="ods-installing.png" >}}

60. Quick test once the installation is done.

{{< figure src="ods-test.png" >}}

## Various other configuration tasks

### Set up environment for users

We need to set some environment variables for all users:

* `PATH`: it makes sense to include `/opt/csw/bin` in the `PATH`, and
   also some directories where Solaris stores its build tools.
* `TZ`: set the time zone. Otherwise R complains about the broken time
   zone setup. 
* `MANPATH`: not strictly required, but handy for interactive users.
* `PKG_CONFIG_PATH`: so that packages that use `pkg-config` find the
  right libraries.

You can add this to the end of the `/etc/profile` file:

```sh
TZ=Europe/London
PATH=/opt/csw/sbin:/opt/csw/bin:/bin:/sbin:/usr/sbin:/usr/bin:/usr/sfw/bin:/usr/sfw/sbin:/usr/ccs/bin
MANPATH=/opt/csw/share/man:/usr/sfw/share/man:/usr/share/man
PKG_CONFIG_PATH=/opt/csw/lib/pkgconfig
export TZ PATH MANPATH PKG_CONFIG_PATH
```

### Make sure that `Xvfb` works

`Xvfb` simulates a GUI session, so e.g. plotting works in our non-GUI
`R CMD check` sessions. The setup is different for Solaris 10 and 11 and
also for Sparc and i386. Some ship two windowing systems, both the old
`Xsun` and the new `Xorg`, so these have two `Xvfb` programs, and they
works slightly differently.

We use the `Xorg` one, that is in `/usr/X11R6/bin`, with a random
display number, in the script that runs our check. See `setup_xcvfb()`
here: https://github.com/r-hub/solarischeck/blob/master/slave.sh

For this to work, we need to set the mode of the `/tmp/.X11-pipe`
directory properly. The only setup that seems to work for all users
(with a warning) is this:

```sh
sudo chmod 1777 /tmp/.X11-pipe/
ls -ld /tmp/.X11-pipe/
#> drwxrwxrwt   2 root     root        1194 Apr 29 08:55 /tmp/.X11-pipe/
```

## Add more software

### TeX

See `install_tex()` in
https://github.com/r-hub/solarischeck/blob/master/install.sh

Quite a lot of TeX packages are needed. Currently:

```sh
function install_tex() {
    sudo pkgutil -y -i \
	 texlive_base \
	 texlive_binaries \
	 texlive_common \
	 texlive_fonts_extra \
	 texlive_fonts_recommended \
	 texlive_latex_base \
	 texlive_latex_base_binaries \
	 texlive_latex_extra \
	 texlive_latex_extra_binaries
}
```

Some TeX packages are huge and take a long time to download.
You can download them manually with `wget`, from the repo at
https://mirror.opencsw.org/opencsw/testing/i386/5.10/ and then uncompress
them with `gunzip` and install them with `pkgadd -d`.
The `wget` download at least shows a progress bar, and you can
also continue downloading a partial file.

If an `.sty` or other TeX file is missing, search at
https://www.opencsw.org/search/ to see which package has it.

### Other system requirements

We have a list of system requirements, for various CRAN packages here:
https://github.com/r-hub/solarischeck/blob/master/sysreqs.txt and
`install.sh` installs them like this currently:

```sh
function install_sysreqs() {
    (
	    set -e
	    tools=$(cat sysreqs.txt)
	    sudo pkgutil -y -i $tools
    )
}
```

### Installing R

We have updated R in OpenCSW, but it has not been published yet,
so `pkgutil` will install an old version currently. You can install a
newer version from R-hub like this:

```sh
function install_r_opencsw() {
    sudo pkgutil -y -i libreadline7
    sudo pkgutil -y -i curl
    sudo pkgutil -t https://files.r-hub.io/opencsw -y -i r_base
}
```

(The `libreadline7` and `curl` packages are a temporary workaround.)

### Building the OpenCSW version of R

See the packaging tutorial here:
https://www.opencsw.org/2012/12/gar-setup-and-packaging-tutorial/

### Building R with OSD

* The R Admin manual has some tips here:
https://cran.r-project.org/doc/manuals/R-admin.html#Solaris
These suggest to add some software manually (in `/usr/local`), but
that does not work very well with OpenCSW. We found it that it is best
to add all software with OpenCSW.

* CRAN has some tips here:
https://www.stats.ox.ac.uk/pub/bdr/Rconfig/r-patched-solaris-x86
These are also useful, but also suggest that some requirements are in
`/usr/local`.

* CRAN's setup (well, some version of it?) is at
http://developer.r-project.org/CRAN/QA/BDR/Solaris/x86/cc/

The setup that actually works well for us is at
https://github.com/r-hub/solarischeck/blob/master/config.site.cc
This worked for R 4.0.0
