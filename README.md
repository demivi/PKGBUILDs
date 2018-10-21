# PKGBUILDs

An Arch Linux repository tailored for my needs. 

The main reasons I created this repository are:
- I want to easily deploy and update all my tools in Docker containers with pacman
- I don't want to bother with AUR helpers
- I want some of my packages to be based on dev versions
- I want to be able to patch some tools without forking
- I want to experiment with package building and repositories

## Usage

Add the following lines to your `/etc/pacman.conf` then run `pacman -Sy`:
```
[mcar]
SigLevel = PackageOptional
Server = https://github.com/demivi/PKGBUILDs/releases/download/current
```
If you want packages in mcar to take precedence over other repositories, put those tree lines higher up in your configuration file.

## nr packages

Here are the reasons you might not want to use the packages starting with `nr` (for Not Recommended):
- cmsmap: the package itselft is lightweith but it requires the `exploitdb` database and clones the 4 supported CMS repositories which makes for an approximative installation size of 1.8 GB...
- eyewitness: this program is bloated, more than 200 dependencies for more than a GB install size
