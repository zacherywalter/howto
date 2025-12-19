# Install
General help on installing programs such as .appimages .desktop .deb files

## make a .desktop entry from a .appimage
Create a .desktop file that points to the application -- here is an example of a .desktop for minecraft:

[Desktop Entry]
Type=Application
Name=Minecraft
Comment=Minecraft
Icon=/home/bram/Applications/Minecraft/icon.png
Exec=/home/bram/Applications/Minecraft/minecraft
Terminal=false
Categories=Minecraft;game
Put that file in ~/.local/share/applications

##### Manually
(source here)[https://askubuntu.com/questions/1328196/how-can-i-create-a-desktop-entry-for-an-appimage]

- Make it executable, run: chmod +x inkscape.AppImage.
- Move it to an appropriate path, like ~/.local/bin.
- Extract the AppImage, run inkscape.AppImage --appimage-extract; a directory will be created called squashfs-root in the current working directory.
- Enter the directory squashfs-root and copy the desktop launcher org.inkscape.Inkscape.desktop to ~/.local/share/applications
- Edit the desktop launcher to point to the path of the AppImage followed by %F or %U or %u, i.e., Exec=/home/username/.local/bin/inkscape.AppImage %F
- Give the .desktop file executable permissions:
- chmod +x ~/.local/share/applications/org.inkscape.Inkscape.desktop
- Remove the directory squashfs-root.

Note: The AppImage file name doesn't have to have .AppImage; the system will know what it is. If the icon isn't displayed, the icon theme you're using is missing the file org.inkscape.Inkscape. You can also edit the desktop launcher to use whatever icon is provided by the icon theme.

##### make .desktop file trusted
(here)[https://forum.xfce.org/viewtopic.php?id=16357]
it needs to be marked executable: `chmod +x FILE`
it needs to have an xfce-exe-checksum metadata entry created for the file:
`f=FILE; gio set -t string $f metadata::xfce-exe-checksum "$(sha256sum $f | awk '{print $1}')"`

## dependencies

##### rdepends
Installing .deb packages and their dependencies
sudo apt install apt-rdepends
apt-rdepends <package>|grep -v "^ "     //lists the dependencies of the package
apt-get download $(apt-rdepends <package>|grep -v "^ " |grep -v "^libc-dev$")
sudo dpkg -i <deb-file>

##### install dependencies for pip python
A Similiar thing to rdepends can be done for python-pip packages
If you want to install a bunch of dependencies from, say a requirements.txt, you would do:

mkdir dependencies
pip download -r requirements.txt -d "./dependencies"
tar cvfz dependencies.tar.gz dependencies

And, once you transfer the dependencies.tar.gz to the machine which does not have internet you can
```bash
tar zxvf dependencies.tar.gz
cd dependencies
pip install * -f ./ --no-index
```
