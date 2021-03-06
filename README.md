mkatlas
=======

[BASH][1] script to build a [texture atlas][2] for small/medium web
sites/games. Requires [ImageMagick][3].

Usage
-----

### Basic

Just run

	$ ./mkatlas img/*

which will create _atlas.png_ and _atlas.json_ with the corresponding sprite regions
in JSON TexturePacker:

	{"frames": {
		"first": {
			"frame" : {"x" : 466, "y" : 0, "w" : 36, "h" : 64}
		},
		"second": {
			"frame" : {"x" : 430, "y" : 0, "w" : 36, "h" : 64}
		},
		...
	}}

Switches
--------

There are a few variables for fine tuning.
Just put them before invocation, e.g.:

	$ ATLAS=atlas.jpg ./mkatlas img/*

#### MAX_SIZE
Maximum width/height of atlas. Default is 2048.

#### ATLAS
File name (and image format) of atlas image.

#### JSON
File name of atlas JSON.

#### OUT
Base file name of Output Atlas Image File and Json File.

[1]: http://en.wikipedia.org/wiki/Bash_(Unix_shell)
[2]: http://en.wikipedia.org/wiki/Texture_atlas
[3]: http://www.imagemagick.org/
