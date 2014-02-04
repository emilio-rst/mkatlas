mkatlas
=======

[BASH][1] script to build a [texture atlas][2] for small/medium web
sites/games. Requires [ImageMagick][3].

Usage
-----

### Basic

Just run

	$ ./mkatlas img/*

which will create _atlas.png_ and outputs the corresponding sprite regions
in JSON format:

	var atlas={
	first:{x:298,y:0,w:35,h:22},
	second:{x:254,y:0,w:44,h:33},
	...
	}

### Advanced

Alternatively you may use just markers in your JavaScript to insert the
frame data in place. This way you wouldn't have to have a extra _atlas_
object and wouldn't need to do any additional mapping. For example:

	var obj = {
		name: "Jim",
		frame: {/*first*/x:0,y:0,w:0,h:0},
		live: 100 };

This file may be patched with _patchatlas_ like this:

	$ ./mkatlas img/* | ./patchatlas index.html

Switches
--------

There are a few variables for fine tuning.
Just put them before invocation, e.g.:

	$ ATLAS=atlas.jpg ./mkatlas img/*

#### WIDTH
Maximum width of atlas. Default is 2048.

#### HEIGHT
Maximum height of atlas. Default is 2048.

#### BORDER
Padding around sprites. Default is 0.

#### ATLAS
File name (and image format) of atlas image.

#### PREFER_LARGER_CELLS
Prefer larger cells for lay out if set. Depending on your sprite set,
that may make a smaller atlas. Just try.

[1]: http://en.wikipedia.org/wiki/Bash_(Unix_shell)
[2]: http://en.wikipedia.org/wiki/Texture_atlas
[3]: http://www.imagemagick.org/
