# OSM to Poster

---

In this tutorial you will learn how to use [OpenStreetMaps](https://www.openstreetmap.org/) to turn any place into a high-quality poster like this:

![.](https://i.imgur.com/ozgEsSf.jpg)

All necessary files and examples are included in this repository, and all software will be free to download. If a program is used that is not freeware a no-costs alternative will be provided. A PDF of this document is included as well.

## What you need

[Map-stylizer](https://github.com/Absolute-Tinkerer/map-stylizer)

Image-editing program (I use Adobe Photoshop in this example, a free alternative would be [Gimp](https://www.gimp.org/) or [Photopea](https://www.photopea.com/)) 

## How to install

Map-stylizer requires Python to run. I use Python 3.9.7, newer versions are untested. You can download the exact version from [here](https://www.python.org/downloads/release/python-397/). Follow the installation instructions and make sure to "add Python to PATH" on Windows. 

Now download or clone the map-stylizer git-repository. You can either do this with [git]() and the command `git clone https://github.com/Absolute-Tinkerer/map-stylizer.git` or by pressing the green "Code"-button and then "Download ZIP" on the github-website.

For the best experience clone this repository as well with `git clone https://github.com/Akashic101/osm-to-poster-tutorial.git`

Open a command-prompt and navigate into the folder, there enter `python main.py` to start the program. If you are getting an error that a module is missing you can install the missing dependency with `pip install <modulename>`. After that run the above command again to start the program. If everything worked you should see the following program open:

![.](https://i.imgur.com/r5i12tD.png)

## How to get OSM-data

Map-stylizer requires a .osm-file which you can get from [OpenStreetMap](https://www.openstreetmap.org/#). Since this tutorial is focused on displaying race-circuits, let's navigate to [Spa-Francorchamps](https://www.openstreetmap.org/relation/6624262#map=15/50.4369/5.9679). There, click on "Export" in the top row, then click on "Manually select a different area" in the left window. Move the window around so it covers the entire circuit plus some some extra padding around it. The more you select the better![](C:\Users\David%20Moll\AppData\Roaming\marktext\images\2022-08-17-10-51-19-image.png)

**Warning:** If you select too much area OSM will not send you data to not clog down the free API. If you see a warning saying "You requested too many nodes (limit is 50000). Either request a smaller area, or use planet.osm" you need to make the selected area smaller. Most nodes are hidden in cities, so try to avoid them. A workaround will be provided down below.

If everything worked out you will get a file called `map.osm`. Save it in `map-stylizer/data` as `<trackname>.osm`. 

If you just want to try out the program first you can use some of the provided example-files. Navigate in your explorer to the "osm-to-poster-tutorial"-folder and in there to "osm-files". You can use any of those files for this tutorial.  
  

## How to create the image

Now that you have the osm-file, navigate back to map-stylizer. Click on "Load OSM-file" and select the file you want in the data-folder. By default you will however not have the basic black-white design like in the above shown poster. If you want this specific style, navigate in your explorer to the "osm-to-poster-tutorial"-folder and in there to "settings". Copy all files and move them to "map-stylizer/configs/user". Now in map-stylizer, click on "Load Settings", then select any of the styles (for starters I recommend `everything.config`. 

You should see something like this:
![.](https://i.imgur.com/6AEow4Q.png)

## How to edit styles

Let's say that you want to change the color of racetracks to red instead of white. For this, open "highway" in "Line settings", then navigate to "raceway". You can see a color-selection under the "Line Settings", if you click on that you can select any color you want. If you want to change how thick the line is you can change the value on the very left under the color-selection. After this you should see something like this:

![.](https://i.imgur.com/34b6pym.png)

## How to render the image

If you are happy with the style you can select the dimension of your image by editing the "Max Dimension"-value under the four buttons at the top. I personally use 6000, which means the image will be 6000px long on its longest axis, in this case height. After this, press "Save Image" and choose the folder you want to save the image in. 

I personally render multiple versions with different styles to make editing easier. All styles are in the "settings"-folder. This however is optional and depends on the style you are going for. 

## Rendering larger areas

Some circuits are larger in area and are not able to be rendered in a single osm-file, circuit de la Sarthe and the Nordschleife are some examples. To fix this you will need some simple math to get the right dimensions. An example is provided in the "tiles"-folder. First you select a part of the area you want to render, this is called a tile. Write down the selected points displayed in OpenStreetMaps in a text-file. Now calculate the difference between the left and right point, and also the top and bottom point. Write those down as well.

For the second image (the tile on the right of the first), keep the top and bottom point, change the left value to the one of the right and add the left-to-right-difference to the right point.

As an example:
```
Tile 1:
Top: 50
Left: 4
Right: 5
Bottom: 48

l-r-difference: 1
t-b-difference: 2

Tile 2:
Top: 50
Left: 5
Right: 6
Bottom: 48
```

For tile 3, the image under the first one, you can use the values of the first tile, but change the top- and bottom-value just like the left- and right-value in the second tile

```
Tile 3:
Top: 48
Left: 4
Right: 5
Bottom: 46
```

Tile 4 is the same, but with the left- and right-value of the second tile

```
Tile 4:
Top: 48
Left: 5
Right: 6
Bottom: 46
```

This of course can be expanded to as many tiles as you need.

Now generate an osm-file of each tile and use each to render an image in map-stylizer. With this you have four images that always have the same dimensions for easier editing.

## Editing the poster

This part is not really a tutorial since each style is unique. I will however list some recourses I used:

* I use [Raleway](https://www.1001freefonts.com/raleway.font) as a font
* If you use logos of circuits or flags try to use a SVG, this way you do not have any loss in quality when scaling them. A great resource for this is Wikimedia
* To see what your poster would look like on a wall you can use [WallApp](https://www.ohmyprints.com/index/455/de/WallApp)
* Render the image as a TIFF for maximum quality when sending it off for print

## Final words

This tutorial and all resources are completly free. If you do however want to help me out consider following me on [Twitch](https://www.twitch.tv/akashic_101) where I stream all kinds of content. If you did used this tutorial to create something you can always send it to me, I would greatly appreciate this