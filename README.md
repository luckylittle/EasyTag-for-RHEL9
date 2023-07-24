# EasyTag-for-RHEL9

![EasyTag](https://github.com/luckylittle/EasyTag-for-RHEL9/assets/8032159/08e0a2d4-e656-4d01-a5f8-42b32c3e303d)

I could not find a better ID3 tagging application on Linux, so I keep using this one. The poject has not been updated in a while and some dependencies are very old, causing dependency hell and [compiling errors](https://gitlab.gnome.org/GNOME/easytag/-/issues/89).

Officially, it is recommended to use one of the two - Flat or Snap:

Flat - https://flathub.org/apps/org.gnome.EasyTAG

Snap - https://snapcraft.io/gnome-easytag

However, I wanted to create an RPM that is usable on RHEL 9, so here it is. It required quite a bit of work, but I was able to build it without much hacking (small changes in the SPEC file and original code due to GCC 11 deprecations).

## Releases

https://github.com/luckylittle/EasyTag-for-RHEL9/releases/tag/2.5.1

## Installation

```bash
# cat /etc/redhat-release
# Red Hat Enterprise Linux release 9.2 (Plow)
sudo dnf install easytag-2.5.1-1.el9.x86_64.rpm id3lib-3.8.3-47.el7.x86_64.rpm
sudo ln -s /usr/local/share/glib-2.0/schemas/org.gnome.EasyTAG.enums.xml /usr/share/glib-2.0/schemas 
sudo ln -s /usr/local/share/glib-2.0/schemas/org.gnome.EasyTAG.gschema.xml /usr/share/glib-2.0/schemas 
sudo glib-compile-schemas /usr/share/glib-2.0/schemas/
easytag --version
```

## Source

https://gitlab.gnome.org/GNOME/easytag
