Installing pre-built packages
=============================

Windows and MacOS
-----------------

If you use Windows or MacOS, you should use the prebuilt releases available
on the project page.


Debian/Ubuntu
-------------

The SLUDGE engine, dev kit and documentation are available in the standard
repositories. All of them can be installed at once with the following command:

```
sudo apt install sludge-engine sludge-devkit sludge-compiler sludge-doc
```

Or pick only the packages you need and install those.


Building from source
====================

Dependencies
------------

On all platforms, you will need at least the following dependencies.

### Dependencies for engine
Dependencies of the OpenSLUDGE engine are SDL, OpenGL, GLEW, libGLU, libpng,
libvpx and xdg-utils. OpenAL sound support requires OpenAL, DUMB and
Alure (>= 1.1) with Vorbis and FLAC support enabled.

On Debian and Ubuntu the corresponding packages can be installed with:
```
sudo apt install libsdl1.2-dev libpng-dev libvpx-dev xdg-utils \
libopenal-dev libalure-dev libvorbis-dev libflac-dev libdumb1-dev
```

Dependencies for OpenGL graphics:
```
sudo apt install mesa-common-dev libglew-dev libglu1-mesa-dev
```

If you want to use OpenGL ES 2 as the graphics library (for mobile devices),
install these instead:
```
sudo apt install libgles2-mesa-dev
```

### Dependencies for Dev Kit

Dependencies of the OpenSLUDGE Dev Kit are GTK+ (>= 2.16), GtkGLExt,
GLEW and libpng.

On Debian and Ubuntu the corresponding packages can be installed with:
```sh
sudo apt install libgtk2.0-dev libgtkglext1-dev libglew-dev libpng-dev
```

Compiling on Windows
--------------------

If you want to compile SLUDGE yourself on Windows, you can use the following
Code::Blocks project files in the `Windows` directory:

* SLUDGE Engine/SLUDGE Engine.cbp
* SLUDGE Development Kit/SLUDGE Development Kit.cbp
* SLUDGE Development Kit/Sprite Bank Editor.cbp

The Windows Dev Kit has so far only been cross-compiled from Debian and Ubuntu
using MinGW. There is a good tutorial on how to do that
[here](https://web.archive.org/web/20110518155024/http://live.gnome.org/GTK+/Win32/Apps).

It should also be possible to compile the Windows Dev Kit on Windows using
MinGW. For running the Windows Dev Kit, the GTK+ runtime package 2.16
(exactly 2.16!) from http://gtk-win.sourceforge.net is required.


Compiling on MacOS
------------------

You can use the Xcode project files in the `Mac Engine` and `Mac Dev Kit` directories.


Compiling on Linux
------------------

Run:
```
./autogen.sh
./configure
make
```

Optionally, to install system-wide (before you do this, make sure you uninstall
any version of SLUDGE installed through your package manager):
```
sudo make install
```

### Configure options

By default only the Engine is built. You can use the following configure options
to (de)select components:

`--disable-engine`
`--enable-devkit`
`--enable-doc`

For example:
```
./configure --disable-engine --enable-devkit
```
will only install the Dev Kit, but not the engine or documentation.

To build everything:
```
./configure --enable-devkit --enable-doc
```

Option `--enable-gles2` will select OpenGL ES 2 as the graphics library.
