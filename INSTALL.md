## By-the-handbook

[![Cooking by the book](https://i.ytimg.com/vi/2PNeNGd50pk/maxresdefault.jpg)](https://www.youtube.com/watch?v=K5tVbVu9Mkg)

### Prep

My LiveCD of choice: [Ubuntu 20.04](https://ubuntu.com/download/desktop)


## Specific configurations

### Portage

Magic command, displays all *global* USE flags currently enabled
```bash
emerge --info | grep ^USE= | cut -d\" -f2
```

make.conf
```bash
nano /etc/portage/make.conf

USE="bluetooth networkmanager pulseaudio"
EMERGE_DEFAULT_OPTS="--ask --ask-enter-invalid --color=y --quiet-build --verbose"
```


### KDE

Enable KDE testing (5.22.1) to be pulled
```bash
mkdir /etc/portage/package.accept_keywords
nano /etc/portage/package.accept_keywords/testing

# Try the newest verstion of KDE Plasma
kde-plasma/plasma-desktop
```

Merge KDE testing and unmask conficting packages
```bash
emerge xorg-x11 plasma-meta --autounmask=y
```

---

## References

Install guides
+ [Gentoo AMD64 Handbook](https://wiki.gentoo.org/wiki/Handbook:AMD64)
+ [Sakaki's EFI Install Guide](https://wiki.gentoo.org/wiki/User:Sakaki/Sakaki%27s_EFI_Install_Guide)
+ [Installing Gentoo Linux EFISTUB On ZFS](https://wiki.gentoo.org/wiki/User:Ali3nx/Installing_Gentoo_Linux_EFISTUB_On_ZFS)
+ [Installing Gentoo Linux On ZFS](https://wiki.gentoo.org/wiki/User:Fearedbliss/Installing_Gentoo_Linux_On_ZFS)
+ [Monsieurp/Gentoo Linux on ZFS](https://wiki.gentoo.org/wiki/User:Monsieurp/Gentoo_Linux_on_ZFS)
+ [Dell XPS 15 7590](https://wiki.gentoo.org/wiki/User:Bugalo/Dell_XPS_15_7590)
+ [Raspberry Pi4 64 Bit Install](https://wiki.gentoo.org/wiki/Raspberry_Pi4_64_Bit_Install)

emerge
+ [Manpage of EMERGE](https://dev.gentoo.org/~zmedico/portage/doc/man/emerge.1.html)
+ [Manpage of PORTAGE](https://dev.gentoo.org/~zmedico/portage/doc/man/portage.5.html)

USE
+ [Global USE flags index](https://packages.gentoo.org/useflags/global)
+ [Gentoo USE Flags - Part 1 - YouTube](https://www.youtube.com/watch?v=pdnJqPR657g)
+ [Gentoo USE Flags - Part 2 - YouTube](https://www.youtube.com/watch?v=IG_paP7NXYI)

unmasking
+ [Help with package.accept_keywords - reddit](https://removeddit.com/r/Gentoo/comments/ndsoy5/help_with_packageaccept_keywords/)
+ [Can anyone explain the autounmask options? - reddit](https://old.reddit.com/r/Gentoo/comments/hpomws/can_anyone_explain_the_autounmask_options/)
