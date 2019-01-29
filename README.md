# DeaDBeeF Lyricbar Plugin
A simple plugin for DeaDBeeF audio player that fetches and shows the lyrics of a song.
It uses [Open Lyrics Database](https://github.com/Lyrics/Lyrics) and if it can't find the song there, it will use [LyricWiki](http://lyrics.wikia.com) as a fallback.
Lyrics found on Open Lyrics Database are then cached in ~/.cache/deadbeef/lyrics.

Inspired by [Infobar Plugin](https://bitbucket.org/dsimbiriatin/deadbeef-infobar/). If you need more functionality,
check [Ignat Loskutov's fork of it](https://bitbucket.org/IgnatLoskutov/deadbeef-infobar-ng), containing a few bug-fixes and minor improvements, but at the moment it has a bug that makes it crash almost all the time with current version of DeaDBeeF.

## Screenshots

<img src="https://raw.githubusercontent.com/C0rn3j/deadbeef-lyricbar/master/screenshots/openlyricsdb.png" width="250"> <img src="https://raw.githubusercontent.com/C0rn3j/deadbeef-lyricbar/master/screenshots/fallback.png" width="250"><img src="https://raw.githubusercontent.com/C0rn3j/deadbeef-lyricbar/master/screenshots/nolyrics.png" width="250">


## Dependencies
To use this plugin, you need to have [gtkmm](http://www.gtkmm.org/) and [libxml++ 3](http://libxmlplusplus.sourceforge.net/) installed.

While gtkmm is available in the repositories of most modern distributions (e.g. in Ubuntu you'll have to install `libgtkmm-3.0-dev` for the gtk3 version of lyricbar), libxml++3 is absent in many of them. If that's the case, you'll have to build it from sources (e.g. for Ubuntu: `sudo apt install checkinstall libxml2-dev && wget http://ftp.gnome.org/pub/GNOME/sources/libxml++/3.0/libxml++-3.0.1.tar.xz && tar -xJf libxml++-3.0.1.tar.xz && cd libxml++-3.0.1 && ./configure --prefix=/usr && make && sudo checkinstall`).

## Installation
### Arch Linux
There's an [AUR package](https://aur.archlinux.org/packages/deadbeef-plugin-lyricbar-git) maintained by dpirate.

### Manual
```sh
git clone https://github.com/C0rn3j/deadbeef-lyricbar
cd deadbeef-lyricbar
make clean gtk3 # or make clean gtk2
sudo cp *.so /usr/lib/deadbeef # Depends on where DeaDBeeF is installed
# OR, to install for the current user only
mkdir -p ~/.local/lib/deadbeef && cp *.so ~/.local/lib/deadbeef
```

## Usage
Activate Design Mode (View → Design mode) and add Lyricbar somewhere.

Personally I like to put the lyrics in a Splitter (left right) with Album cover on one side, as you can see on the screenshots.

Disable Design Mode back and enjoy the music :)
