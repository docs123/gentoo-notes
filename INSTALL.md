## By-the-handbook

[![Cooking by the book](https://i.ytimg.com/vi/2PNeNGd50pk/maxresdefault.jpg)](https://www.youtube.com/watch?v=K5tVbVu9Mkg)

### Preparation

My LiveCD of choice: [Ubuntu 20.04](https://ubuntu.com/download/desktop)

### Classic procedure

Edit later


## Specific configurations

### Portage

Magic command, displays all *global* USE flags currently enabled
```bash
emerge --info | grep ^USE= | cut -d\" -f2
```

or better, with `euse` from `gentoolkit`
```bash
euse -a
```

Personalize `make.conf`
```bash
nano /etc/portage/make.conf

USE="bluetooth networkmanager pulseaudio"
EMERGE_DEFAULT_OPTS="--ask --ask-enter-invalid --color=y --quiet-build --verbose"
```

### Useful packages

```bash
emerge bash-completion gentoolkit sudo rcs
```

Setup things immediatly
```bash
nano /etc/dispatch-conf.conf

use-rcs=yes
```

### KDE

Allow KDE testing (5.22.1) to be pulled
```bash
mkdir /etc/portage/package.accept_keywords
nano /etc/portage/package.accept_keywords/testing

# Try the newest version of KDE Plasma
kde-plasma/plasma-desktop
```

Merge `plasma-desktop` and unmask conficting packages
```bash
emerge plasma-desktop --autounmask-write
dispatch-conf
emerge plasma-desktop
```

Merge Xorg
```bash
emerge xorg-x11
```

## Post-installation with systemd

Time zone
```bash
timedatectl list-timezones
timedatectl set Europe/Paris
timedatectl
```

Hostname
```bash
hostnamectl set-hostname toaster
hostnamectl status
```

Locales
```bash
eselect locale list
eselect locale set X
source /etc/locale
localectl
```

Keymaps
```bash
# VC Keymap
localectl list-keymaps

# X11 Layout
localectl list-x11-keymap-layouts
```

Pretty much self-explanatory
```bash
systemctl enable NetworkManager
systemctl start NetworkManager
systemctl enable bluetooth
systemctl start bluetooth
```
---

## References

+ ### Install guides
+ [Gentoo AMD64 Handbook](https://wiki.gentoo.org/wiki/Handbook:AMD64)
+ [Sakaki's EFI Install Guide](https://wiki.gentoo.org/wiki/User:Sakaki/Sakaki%27s_EFI_Install_Guide)
+ [Installing Gentoo Linux EFISTUB On ZFS](https://wiki.gentoo.org/wiki/User:Ali3nx/Installing_Gentoo_Linux_EFISTUB_On_ZFS)
+ [Installing Gentoo Linux On ZFS](https://wiki.gentoo.org/wiki/User:Fearedbliss/Installing_Gentoo_Linux_On_ZFS)
+ [Monsieurp/Gentoo Linux on ZFS](https://wiki.gentoo.org/wiki/User:Monsieurp/Gentoo_Linux_on_ZFS)
+ [Dell XPS 15 7590](https://wiki.gentoo.org/wiki/User:Bugalo/Dell_XPS_15_7590)
+ [Raspberry Pi4 64 Bit Install](https://wiki.gentoo.org/wiki/Raspberry_Pi4_64_Bit_Install)

+ ### EFI/ESP/GPT/MBR/BIOS/UEFI ...
+ [Is there sense in mounting EFI partition at /boot? - Ask Ubuntu](https://askubuntu.com/questions/928161/is-there-sense-in-mounting-efi-partition-at-boot)
+ [EFI System Partition](https://wiki.gentoo.org/wiki/EFI_System_Partition)
+ [Discussion page in Gentoo Handbook — how to use grub2 with ESP](https://wiki.gentoo.org/wiki/Handbook_Talk:AMD64/Full/Installation#improve_suggested_partitions_and_use_of_grub-install)

+ ### emerge
+ [Manpage of EMERGE](https://dev.gentoo.org/~zmedico/portage/doc/man/emerge.1.html)
+ [Manpage of PORTAGE](https://dev.gentoo.org/~zmedico/portage/doc/man/portage.5.html)
+ [dispatch-conf on Gentoo Linux - YouTube](https://www.youtube.com/watch?v=en-aLJGXEqI)

  + ### USE
  + [Global USE flags index](https://packages.gentoo.org/useflags/global)
  + [Gentoo USE Flags - Part 1 - YouTube](https://www.youtube.com/watch?v=pdnJqPR657g)
  + [Gentoo USE Flags - Part 2 - YouTube](https://www.youtube.com/watch?v=IG_paP7NXYI)

  + ### accept_keywords
  + [Help with package.accept_keywords - reddit](https://removeddit.com/r/Gentoo/comments/ndsoy5/help_with_packageaccept_keywords/)
  + [Can anyone explain the autounmask options? - reddit](https://old.reddit.com/r/Gentoo/comments/hpomws/can_anyone_explain_the_autounmask_options/)

+ ### systemd
+ [Configuring systemd and Installing Necessary Tools](https://wiki.gentoo.org/wiki/User:Sakaki/Sakaki%27s_EFI_Install_Guide/Configuring_systemd_and_Installing_Necessary_Tools#Re-establishing_Networking_and_ssh)

  + ### Locales
  + [Gentoo Localization Guide](https://wiki.gentoo.org/wiki/Localization/Guide)
  + [System time](https://wiki.gentoo.org/wiki/System_time#systemd)
