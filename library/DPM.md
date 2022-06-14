# Debian Package Manager

dpkg is a debian package management tool to install, build, remove, query and manage packages.

Syntax: `dpkg [option...] action`

- Install a package
`dpkg -i [deb_packagefile]`
- Check if a package is installed
`dpkg -s [package_name]`
- Remove an installed package
`dpkg -r [package_name]`
- Purge an installed package
`dpkg -P [package_name]`
- List installed packages
`dpkg -l` add [package_name] for listing a particular package only
- List content of .deb package
`dpkg -c [deb_packagefile]`
- Show information of .deb package
`dpkg -i [deb_packagefile]`
- Extract files of a package
`dpkg -x [deb_packagefile] [directory]`
- Unpack, without configuring, a package
`dpkg --unpack [deb_packagefile]` status will be unpacked
- Reconfigure an unpacked package
`dpkg --configure [packagename]` this changes its status to installed
- Search partially installed packages
`dpkg -C`
- List all files of installed package
`dpkg -L [package_name]`
- Search filename of installed package. Prints every file that contains the pattern
`dpkg -S [pattern]`
- Update package information
`dpkg --update-avail [package_name]`

