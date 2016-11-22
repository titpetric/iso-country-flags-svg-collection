# ISO country flags SVG collection - high quality vector graphics country flag icons

## Description
This repository contains 248 country flag SVG icons as shown in the following sheet:

![iso-country-flags-sheet-flat.png](https://raw.github.com/koppi/iso-country-flags-svg-collection/master/examples/iso-country-flags-sheet-flat.png "ISO country flags svg collection")

You can build the above icon sheet with different icon styles using the templates in the build directory: flat, simple, fancy, glossy:

![templates.png](https://raw.github.com/koppi/iso-country-flags-svg-collection/master/examples/templates.png "Country flag icons templates")

Simply type

```
$ make -j4
```

to build PNG versions of the country flags contained in this collection. This will create about 320MB of data: flat, simple, fancy, glossy template based PNG files with the following resolutions: "512x512 (web), 256x256, 128x128, 96x96, 72x72, 64x64, 48x48, 36x36, 32x32, 24x24, 16x16".

For example the results with the template "flat" applied to the "United States" country flag icon looks like follows:

![resolutions.png](https://raw.github.com/koppi/iso-country-flags-svg-collection/master/examples/resolutions.png "Country flag icon resoultions")
 
### Usage examples

Type

```
$ make help
```

to see all build targets.

* Country flags icon sheets - type ```$ make -j4 sheets```.

* Google Earth - [G+ users of the world - KMZ file](http://goo.gl/YJjv3):

  ![G+ users of the world KMZ file](https://raw.github.com/koppi/iso-country-flags-svg-collection/master/examples/example-google-earth.png). Run the following command to generate all the kml files with different country name translations: ```$ make kml```, a shortcut for the command: ```$ scripts/build.pl --cmd example kml --json iso-3166-1.json --out build --res 16x16 --lang all```.

* [WebGL Earth - ISO country flags](http://tinyurl.com/webgl-earth-iso-country-flags).

  ![WebGL Earth - ISO country flags](https://raw.github.com/koppi/iso-country-flags-svg-collection/master/examples/example-webgl-earth.png). Open the [live demo](http://tinyurl.com/webgl-earth-iso-country-flags) in your web browser. This demo uses a slightly modified [iso-3166-1.json file](http://dl.dropbox.com/u/3139257/iso-country-flags-svg-collection/examples/iso-3166-1.json) (with an added "var data = " string) an the [WebGL Earth API](http://www.webglearth.org/).

* Google Maps - [G+ users of the world - PicasaWeb album](http://goo.gl/mHyJb):

  ![G+ users of the world picasaweb album](https://raw.github.com/koppi/iso-country-flags-svg-collection/master/examples/example-google-maps.png) Notice: you first have to zoom out to see anything on the world map (it seems, that there is a bug in Google Maps, which prevents to show the country icons).

* Xplanet - [howto generate xplanet marker config files](https://github.com/koppi/iso-country-flags-svg-collection/wiki/example-xplanet):

  ![example-xplanet-de](https://raw.github.com/koppi/iso-country-flags-svg-collection/master/examples/example-xplanet-de.png) Notice: go to the [Wiki](https://github.com/koppi/iso-country-flags-svg-collection/wiki/example-xplanet). for howto generate xplanet marker config files. Run the following command to generate all the xplanet marker config files: ```$ make -j4 xplanet```, a shortcut for the command: ```$ scripts/build.pl --cmd example xplanet --json iso-3166-1.json --out build --res 16x16 --lang all```.
  
## Download the icon sets

You can download pre built png icon sets from my [dropbox folder](http://goo.gl/oaoEl).

## Building the icon sets

### Requirements / Dependencies

For converting the SVG files to different formats using different templates, you need to install the following software packages:

* librsvg - an SVG rendering library associated with the Gnome Project.
* Perl Modules: XML::LibXML, JSON.
* ImageMagick [here](http://www.imagemagick.org/).

On Debian/Ubuntu you can install these packages with the following command:

```
 $ sudo apt-get -y install imagemagick libxml-libxml-perl libjson-perl librsvg2-bin
```

Simply type "make" to generate the icon sets. By default the Makefile generates icon sets with the following resolutions.

For the country-squared svg files:

```
512x512 256x256 128x128 96x96 72x72 64x64 48x48 36x36 32x32 24x24 16x16
```

And for the country-4x3 svg files:

```
1280x960 640x480 320x240 160x120 80x60 40x30 20x15
```

### Building your own icon sets

If you want to build your own icon sets with the same templates used for the flags here, you just create a folder under [svg/](https://github.com/koppi/iso-country-flags-svg-collection/tree/master/svg), and drop your .svg files in there. Run make to (re-)generate the output.

Country flag examples use a surface area of 512x512 (1:1) and 640x480 (4:3), so be sure to keep the 1:1 or 4:3 ratios for best results.

#### Building with custom resolutions

You can generate custom icon set resolutions (e.g. "5x5 8x8") by creating a file:

 * "build/country-squared.res", or
 * "build/country-4x3.res",
 
which looks like follows:

```
5x5 8x8
```

Typing "make" will then generate icon sets with the resolutions defined above for all country-squared/4x3 icons.

#### Generating the icon sheet files

Type "make sheets" to generate icon sheets for the icon sets created above.

#### Adding local build targets

You can add your local build target commands to the Makefile.local, which gets invoked with the "all" target of the main Makefile.

### Are you using this country flags collection?

Want to be featured in a gallery of apps using it? Then please send a screenshot and details of your app to [Jakob Flierl](https://github.com/koppi).

## Authors / TODO / License

The country flag icons in this repository were collected from Wikipedia Commons project during the [EUHackathon 2011](http://www.euhackathon.eu/). We did not find an up to date free collection of SVG vector graphics icons during the hack marathon. So we decided to build up this collection and share it here with future EUHackathoners and the Internet.

Initial import of the iso-country-flags-collection to github - [Jakob Flierl](https://github.com/koppi). We try to keep the TODO list short. You can [browse issues](https://github.com/koppi/iso-country-flags-svg-collection/issues) related to iso-country-flags-svg-collection to see, what's being worked on.

Most of the country flag icons are licensed under the [Public Domain](http://en.wikipedia.org/wiki/Public_domain).
