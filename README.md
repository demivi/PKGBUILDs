# PKGBUILDs

An Arch Linux repository tailored for my needs. 

The main reasons I created this repository are:
- I use Docker a lot and I want to easily deploy and update containers with pacman
- I don't want to bother with AUR helpers, I only want to use pacman
- Some of my coworkers have similar needs
- I want to experiment with package building and repositories

Some of the PKGBUILD files are straight up stolen from AUR.

## Usage

Add the following lines to your `/etc/pacman.conf` then run `pacman -Sy`:
```
[adv]
Server = https://github.com/demivi/PKGBUILDs/releases/download/current
SigLevel = PackageOptional
```

## nr packages

Here are the reasons you might not want to use the packages starting with `nr` (for Not Recommended):
- cmsmap: the package itselft is lightweith but it requires the `exploitdb` database and clones the 4 supported CMS repositories which makes for an approximative installation size of 1.8 Go...
