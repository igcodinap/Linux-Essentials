# APT
## Files related
- Ubuntu repository list is stored in `/etc/apt/sources.list`. All packages are pulled from these.

### apt
Used for install, update, remove or query packages and their dependencies. Suitted for better interactive usage compared to apt-... tools.

Syntax: `apt [-h] [-o=config_string] [-c=config_file] [-t=target_release] [-a=architecture] {list | search | show | update | install pkg [{=pkg_version_number | /target_release}]...  | remove pkg...  | upgrade | full-upgrade | edit-sources | {-v | --version} | {-h | --help}}`

- Install a package
`apt install [package_name...]`
- Remove a package
`apt remove [package_name]`
To also delete configuration files
`apt purge [package_name]`
- Show Package details
`apt show [package_name]`
- Search for pattern in name and description of packages
`apt search [pattern]`
- Update the available packages' list
`apt update`
- Upgrade packages
`apt upgrade`
- List the upgradable packages
`apt list --upgradable`
- Upgrade the system
`apt full-upgrade`
- Remove unused packages
`apt autoremove`
- List all packages
`apt list`
- List installed packages
`apt list --installed`
- Check packages' dependencies
`apt depends [package_name]`


### apt-get
You will see that the options in apt-get are closely related to the ones in apt

Syntax:        `apt-get [-asqdyfmubV] [-o=config_string] [-c=config_file] [-t=target_release]
               [-a=architecture] {update | upgrade | dselect-upgrade | dist-upgrade |
               install pkg [{=pkg_version_number | /target_release}]...  | remove pkg...  |
               purge pkg...  | source pkg [{=pkg_version_number | /target_release}]...  |
               build-dep pkg [{=pkg_version_number | /target_release}]...  |
               download pkg [{=pkg_version_number | /target_release}]...  | check | clean |
               autoclean | autoremove | {-v | --version} | {-h | --help}}`

- Install a package
`apt-get [package_name...]`
- Upgrade a package
`apt-get upgrade [package_name]`
- Upgrade all installed packages
`apt-get upgrade`
- Update all installed packages
`apt-get update`
- Search for newer dependencies versions, install new packages and remove old ones:
`apt-get dist-upgrade`
- Remove a package
`apt-get remove [package_name]` 
For deleting also its configurations files run `apt-get purge [package_name]`
- Remove unnecessary packages
`apt-get autoremove`
- Update package cache and check for broken dependencies
`apt-get check`