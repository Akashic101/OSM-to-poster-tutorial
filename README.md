# OSM to Poster

---

In this tutorial you will learn how to use [OpenStreetMaps](https://www.openstreetmap.org/) to turn any place into a high-quality poster like this:

![.](C:\Users\David%20Moll\Downloads\wallapp-17082022-102804.jpg)

All necessary files and examples are included in this repository, and all software will be free to download. If a program is used that is not freeware a no-costs alternative will be provided.

## What you need

[Map-stylizer](https://github.com/Absolute-Tinkerer/map-stylizer)

Image-editing program (I use Adobe Photoshop in this example, a free alternative would be [Gimp](https://www.gimp.org/) or [Photopea](https://www.photopea.com/)) 

## How to install

Map-stylizer requires Python to run. I use Python 3.9.7, newer versions are untested. You can download the exact version from [here]([Python Release Python 3.9.7 | Python.org](https://www.python.org/downloads/release/python-397/)). Follow the installation instructions and make sure to "add Python to PATH" on Windows. 

Now download or clone the map-stylizer git-repository. You can either do this with [git]([Git - Downloads](https://git-scm.com/downloads)) and the command `git clone https://github.com/Absolute-Tinkerer/map-stylizer.git` or by pressing the green "Code"-button and then "Download ZIP" on the github-website.

For the best experience clone this repository as well with `git clone https://github.com/Akashic101/osm-to-poster-tutorial.git`

Open a command-prompt and navigate into the folder, there enter `python main.py` to start the program. If you are getting an error that a module is missing you can install the missing dependency with `pip install <modulename>`. After that run the above command again to start the program. If everything worked you should see the following program open:

![](C:\Users\David%20Moll\AppData\Roaming\marktext\images\2022-08-17-10-45-22-image.png)

## How to get OSM-data

Map-stylizer requires a .osm-file which you can get from [OpenStreetMap](https://www.openstreetmap.org/#). Since this tutorial is focused on displaying race-circuits, let's navigate to [Spa-Francorchamps](https://www.openstreetmap.org/relation/6624262#map=15/50.4369/5.9679). There, click on "Export" in the top row, then click on "Manually select a different area" in the left window. Move the window around so it covers the entire circuit plus some some extra padding around it. The more you select the better![](C:\Users\David%20Moll\AppData\Roaming\marktext\images\2022-08-17-10-51-19-image.png)

**Warning:** If you select too much area OSM will not send you data to not clog down the free API. If you see a warning saying "You requested too many nodes (limit is 50000). Either request a smaller area, or use planet.osm" you need to make the selected area smaller. Most nodes are hidden in cities, so try to avoid them. A workaround will be provided down below.

If everything worked out you will get a file called `map.osm`. Save it in `map-stylizer/data` as `<trackname>.osm`. 

If you just want to try out the program first you can use some of the provided example-files. Navigate in your explorer to the "osm-to-poster-tutorial"-folder and in there to "osm-files". You can use any of those files for this tutorial.

## How to create the image

Now that you have the osm-file, navigate back to map-stylizer. Click on "Load OSM-file" and select the file you want in the data-folder. By default you will however not have the basic black-white design like in the above shown poster. If you want this specific style, navigate in your explorer to the "osm-to-poster-tutorial"-folder and in there to "settings". Copy all files and move them to "map-stylizer/configs/user". Now in map-stylizer, click on "Load Settings", then select any of the styles (for starters I recommend `everything.config`. 
