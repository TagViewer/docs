---
description: How to install TagViewer.
---

# Installation

Begin by opening the latest release on GitHub. There, you'll see the binaries and packages. If you know what you're doing, just download the one you need. If not, continue reading.

## Windows

Squirrel.Windows does not work on Linux or Windows \(at least for me\). Therefore, for now there are no binaries available for Windows. If you are able to package the application on Windows, please [contact me](mailto:mattf53190@gmail.com?subject=TagViewer:+I+can+package+for+Windows) so I can add it to the releases. Please follow the manual installation instructions for Windows below.

## MacOS

Download the MacOS zip and extract it. The only file is the binary. Double-click on it or right-click and select "Open" to start TagViewer.

## Linux

### Debian-based Distros

Download the .deb and install it.

### RPM-based Distros

Download the .rpm and install it.

### `pacman` Distros

Download the PKGBUILD, put it in its own directory \(for example, `~/Downloads/tagviewer`\), and install it with `makepkg -si`. I would include the PKGBUILD in the repository, but I can't figure out how to make a checksum for a directory that contains a file that contains that checksum!

### Snap, Flatpak, etc.

Snaps, Flatpaks, and any other similar formats are not supported. We suggest that you follow one of the above options instead.

## Manual Installation

If your operating system isn't currently supported, you can also perform a manual installation. Begin by downloading the .zip package for your operating system \(not the source code at the bottom of the binaries list\). Extract it in a temporary location. Then follow the steps below for your operating system.

### Windows

Move all of the contents to `C:\Program Files\TagViewer` \(You need to create that directory\). If you want, make a shortcut on the desktop, by right-clicking and selecting `New / Shortcut`. For the target, input `C:\Program Files\TagViewer\tagviewer.exe`. You can name the shortcut anything you like, but I suggest "TagViewer". Create the shortcut. You'll need to select the correct icon, so right-click on the shortcut and select Properties. Near the bottom of the popup window, click on Change Icon. Click Browse in the popup window. Input `C:\Program Files\TagViewer\resources\app\icons\macwin\icon.ico`. Click OK and exit the popups. TagViewer is now installed on your system.

### Mac

N/A. See above.

### Linux

* Install the following dependencies \(if any of them are not available, you probably don't need them\):
  * libgtk-3-0
  * libnotify4
  * libnss3
  * libxss1
  * libxtst6
  * xdg-utils
  * libatspi2.0-0
  * libdrm2
  * libgbm1
  * libxcb-dri3-0
  * kde-cli-tools \| kde-runtime \| trash-cli \| libglib2.0-bin \| gvfs-bin \(any one of these\)
* Copy all of the contents inside the folder to `/usr/lib/tagviewer`.
* Create a .desktop file in `/usr/share/applications` with the following contents:

{% code title="/usr/share/applications/tagviewer.desktop" %}
```text
[Desktop Entry]
Name=tagviewer
Comment=A simple program that allows viewing of images under any tag, as well as modifying those tags.
GenericName=Media Organizer
Exec=tagviewer
Icon=tagviewer
Type=Application
StartupNotify=true
Categories=Utility;Graphics;
```
{% endcode %}

* Create an empty file at `/usr/share/lintian/overrides/tagviewer`. You may need to create the directories.
* Copy the file at the relative path `tagviewer-linux-x64/resources/app/icons/png/512x512.png` to `/usr/share/pixmaps/tagviewer.png`.
* Make a symlink from `/usr/bin/tagviewer` to `/usr/lib/tagviewer/tagviewer`.
* Optionally, copy the same .desktop file above to your desktop to have a shortcut.

Alternatively, enter the commands below in the terminal, from the `tagviewer-linux-x64` folder. You may need to give your password, but rest assured that it is only used to copy files into system directories, and the below commands do exactly what is listed above.

```bash
sudo su
mkdir -p /usr/lib/tagviewer
cp -r . /usr/lib/tagviewer
cat << EOF > /usr/share/applications/tagviewer.desktop
[Desktop Entry]
Name=tagviewer
Comment=A simple program that allows viewing of images under any tag, as well as modifying those tags.
GenericName=Media Organizer
Exec=tagviewer
Icon=tagviewer
Type=Application
StartupNotify=true
Categories=Utility;Graphics;
EOF
chmod +x /usr/share/applications/tagviewer.desktop
mkdir -p /usr/share/lintian/overrides
touch /usr/share/lintian/overrides/tagviewer
cp resources/app/icons/png/1024x1024.png /usr/share/pixmaps/tagviewer.png
ln -s /usr/lib/tagviewer/tagviewer /usr/bin/tagviewer
exit
```

And to copy the shortcut from /usr/share/applications/tagviewer.desktop to your desktop, run the following:

```bash
cp /usr/share/applications/tagviewer.desktop ~/Desktop/tagviewer.desktop
```

### Uninstallation

To uninstall TagViewer, delete all files you created/copied while installing. No other interventions are necessary.

