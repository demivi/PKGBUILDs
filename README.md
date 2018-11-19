# PKGBUILDs

An Arch Linux repository tailored for my needs. 

The main reasons I created this repository are:
- I want to easily deploy and update all my tools in Docker containers with pacman
- I don't want to bother with AUR helpers
- I want some of my packages to be based on dev versions
- I want to be able to patch some tools without forking
- I want to experiment with package building and repositories

I use most of these packages in Docker containers with my Compose wrapper:
https://github.com/demivi/cpw

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
mcar/crackmapexec
mcar/impacket
community/impacket
community/metasploit
archstrike/crackmapexec
```

## nr packages

Here are the reasons you might not want to use the packages starting with `nr` (for Not Recommended):
- cmsmap: the package itselft is lightweith but it requires the `exploitdb` database and clones the 4 supported CMS repositories which makes for an approximative installation size of 1.8 GB...
- eyewitness: this program is bloated, more than 200 dependencies for more than a GB install size
