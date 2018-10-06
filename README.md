# PKGBUILDs

An Arch Linux repository tailored for my needs. 

The main reasons I created this repository are:
- I use Docker a lot and I want to easily deploy and update containers with pacman
- I don't want to bother with AUR helpers, I only want to use pacman
- Some of my coworkers have similar needs so I maintain packages for them
- I want to experiment with pakage building and repositories

Some of the PKGBUILD files are straight up stolen from AUR.

## Usage

Add the following lines to your `/etc/pacman.conf` then run `pacman -Sy`:
```
[rco]
Server = https://github.com/demivi/PKGBUILDs/releases/download/current
SigLevel = PackageOptional
```
