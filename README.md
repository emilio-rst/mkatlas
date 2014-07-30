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
in JSON format for Phaser:

	{"frames": {
		"first": {
			"frame" : {"x" : 466, "y" : 0, "w" : 36, "h" : 64},
			"spriteSourceSize" : {"x" : 0, "y" : 0, "w" : 36, "h" : 64},
			"sourceSize" : {"w" : 36 , "h" : 64}
		},
		"second": {
			"frame" : {"x" : 430, "y" : 0, "w" : 36, "h" : 64},
			"spriteSourceSize" : {"x" : 0, "y" : 0, "w" : 36, "h" : 64},
			"sourceSize" : {"w" : 36 , "h" : 64}
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

#### BORDER
Padding around sprites. Default is 0.

#### ATLAS
File name (and image format) of atlas image.

#### JSON
File name of atlas JSON.

[1]: http://en.wikipedia.org/wiki/Bash_(Unix_shell)
[2]: http://en.wikipedia.org/wiki/Texture_atlas
[3]: http://www.imagemagick.org/
