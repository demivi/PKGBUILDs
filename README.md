# PKGBUILDs

An Arch Linux repository with a focus on security to complement existing ones (ArchStrike, BlackArch).

The main reasons I created this repository are:

- I want to easily deploy and update all my pentest tools in Docker containers with pacman
- I don't want to use AUR helpers in Docker containers if I can avoid it
- I want some of my packages to be based on dev versions
- I want to be able to patch some tools without forking
- I want to experiment with package building and repositories

I use most of these packages in Docker containers with my Compose wrapper:

https://github.com/demivi/cpw

To simplify things I edit the existing Github release instead of creating new ones every time a package is updated. If you want to track the repository updates, check the commits instead of the release page.

## Usage

Add the following lines to your `/etc/pacman.conf` then run `pacman -Sy`:
```
[mcar]
SigLevel = PackageOptional
Server = https://github.com/demivi/PKGBUILDs/releases/download/current
```
If you want packages in mcar to take precedence over other repositories, put those tree lines higher up in your configuration file. Otherwise, you will need to specify `mcar/` before the names of the packages you want to install from this repository.

If you don't already use it, I suggest looking into pkgfile which will help you identify packages by the commands they provide:
```
# pkgfile secretsdump.py
mcar/impacket
community/impacket
community/metasploit
archstrike/crackmapexec
```

This complements pacman -Ss very well.

## dev packages

The following packages are meant to be based on dev versions:

- cmsmap
- dex2jar
- drozer
- enjarify
- enum4linux
- impacket
- nikto
- rdp-screenshotter
- responder
- smbmap
- testssl.sh
- wafw00f
- wifite

Note that enjarify and responder packages are based on maintained forks (from the original author regarding responder).

## cmsmap warning

The package itselft is lightweith but it requires the `exploitdb` database and clones the 4 supported CMS repositories at first start which makes for an approximative installation size of 1.8 GB...
