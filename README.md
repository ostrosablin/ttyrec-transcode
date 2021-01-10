# ttyrec-transcode

## Simple script to transcode ttyrec from one encoding to another.

Designed particularly to transcode ttyrecs from NetHack public servers (with IBMGraphics, CP437) into UTF-8 ttyrecs that can be played back in any modern terminal emulator. However, should work with any pair of encodings, as long as characters displayed in ttyrec are present in both encodings.

This script is a derivative of [pyttygif's ttyplay.py module](https://github.com/tmp6154/pyttygif/blob/master/pyttygif/ttyplay.py), and it re-uses ttyrec player for reading ttyrecs and adds a ttyrec writer to write transcoded records back.

## Here's an example of a transcoded ttyrec:

![ttyrec before transcoding, IBMGraphics (CP437 encoding)](https://github.com/tmp6154/ttyrec-transcode/blob/master/img/src.png?raw=true "ttyrec in CP437 encoding, looks garbled on UTF-8 terminal")
![ttyrec after transcoding, UTF-8](https://github.com/tmp6154/ttyrec-transcode/blob/master/img/dst.png?raw=true "ttyrec in UTF-8 encoding after processing by ttyrec-transcode, plays back fine on UTF-8 terminal")

## How to use this script

This script can be run on any Python 3.6+ and has no external dependencies. Just grab a copy of ttyrec-transcode.py from this repo.

If you wish to create a new transcoded file from your ttyrec, use it like this:

    python3 ttyrec-transcode.py cp437 utf-8 non_playable.ttyrec -o fixed.ttyrec

This will read a non_playable.ttyrec file with CP437 encoding and will produce a new fixed.ttyrec file with UTF-8 encoding, which can be later played with ttyplay on a regular UTF-8 terminal without hassle.

However, you might want to use it directly, without producing any intermediate files, perhaps, to feed the output right to the ttyplay. This scenario is also supported by ttyrec-transcode. Just omit the **-o** option, and program will output transcoded ttyrec output directly to stdout, from where you might pipe or redirect it.

    python3 ttyrec-transcode.py cp437 utf-8 non_playable.ttyrec | ttyplay

That's all there to it.

## License

![GPLv3](https://github.com/tmp6154/ttyrec-transcode/blob/master/img/gplv3.png?raw=true "GPLv3")
