<div align="center" markdown>
<img src="https://github.com/iwatkot/maps4fs/assets/118521851/ffd7f0a3-e317-4c3f-911f-2c2fb736fbfa">

<p align="center">
  <a href="#Quick-Start">Quick Start</a> •
  <a href="#Overview">Overview</a> • 
  <a href="#Features">Features</a> • 
  <a href="#Supported-objects">Supported objects</a> • 
  <a href="#How-To-Run">How-To-Run</a> • 
  <a href="Settings">Settings</a> • 
  <a href="#Bugs-and-feature-requests">Bugs and feature requests</a>
</p>

![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/iwatkot/maps4fs)
![GitHub downloads](https://img.shields.io/github/downloads/iwatkot/maps4fs/total)
![GitHub issues](https://img.shields.io/github/issues/iwatkot/maps4fs)
[![Maintainability](https://api.codeclimate.com/v1/badges/b922fd0a7188d37e61de/maintainability)](https://codeclimate.com/github/iwatkot/maps4fs/maintainability) 

</div>

## Quick Start
For those, who don't want to read anything, here you go:<br>
**Option 1:** launch the [@maps4fs](https://t.me/maps4fsbot) Telegram bot and generate a map template in a few clicks.<br>
**Option 2:** run the Docker version in your browser. Launch the following command in your terminal:
```bash
docker run -d -p 8501:8501 iwatkot/maps4fs
```
And open [http://localhost:8501](http://localhost:8501) in your browser.<br>
If you don't know how to use Docker, navigate to the [Docker version](#option-2-docker-version), it's really simple.<br>

## Overview
The core idea is coming from the awesome [maps4cim](https://github.com/klamann/maps4cim) project.<br>

<a href="https://www.youtube.com/watch?v=ujwWKHVKsw8" target="_blank"><img src="https://github.com/user-attachments/assets/7df532d2-2909-4241-b4ca-d5b7dc4502e4"/></a>
<i>Video tutorial: How to generate a Farming Simulator 22 map from real-world data.</i>


The main goal of this project is to generate map templates, based on real-world data, for the Farming Simulator. It's important to mention that **templates are not maps**. They are just a starting point for creating a map. This tool just uses built-in textures to highlight different types of terrain and buildings with correct shapes and scales and to generate a height map. The rest of the work is up to you. So if you thought that you could just run this tool and get a playable map, then I'm sorry to disappoint you. But if you are a map maker, then this tool will save you a lot of time.<br>
So, if you're new to map making, here's a quick overview of the process:
1. Generate a map template using this tool.
2. Download the Giants Editor.
3. Open the map template in the Giants Editor.
4. Now you can start creating your map (adding roads, fields, buildings, etc.).

## Features
- Allows to enter a location by lat and lon (e.g. from Google Maps).
- Allows to select a size of the map (2x2, 4x4, 8x8 km, 16x16 km).
- Generates a map template (check the list of supported objects in [this section](#supported-objects)).
- Generates a height map.

## Supported objects
The project is based on the [OpenStreetMap](https://www.openstreetmap.org/) data. So, refer to [this page](https://wiki.openstreetmap.org/wiki/Map_Features) to understand the list below.
- "building": True
- "highway": ["motorway", "trunk", "primary"]
- "highway": ["secondary", "tertiary", "road"]
- "highway": ["unclassified", "residential", "track"]
- "natural": "grassland"
- "landuse": "farmland"
- "natural": ["water"]
- "waterway": True
- "natural": ["wood", "tree_row"]

The list will be updated as the project develops.

## How-To-Run
### Option 1: Telegram bot
🟢 Recommended for all users, you don't need to install anything.<br>
Using Telegram bot [@maps4fs](https://t.me/maps4fsbot).<br>
Note: due to CPU and RAM limitations of the hosting, only 2x2 and 4x4 km maps are available. If you need bigger maps, use the [Docker version](#option-2-docker-version).<br>

![Telegram bot](https://github.com/iwatkot/maps4fs/assets/118521851/ede69fe8-1a34-4ede-908f-52c9dc355ae4)
<br>

Using it is easy and doesn't require any guides. Enjoy!

### Option 2: Docker version
🟢 Recommended for users who need bigger maps, very simple installation.<br>
You can launch the project with minimalistic UI in your browser using Docker. Follow these steps:

1. Install [Docker](https://docs.docker.com/get-docker/) for your OS.
2. Run the following command in your terminal:
```bash
docker run -d -p 8501:8501 iwatkot/maps4fs
```
3. Open your browser and go to [http://localhost:8501](http://localhost:8501).
4. Fill in the required fields and click on the `Generate` button.
5. When the map is generated click on the `Download` button to get the map.

![WebUI](https://github.com/user-attachments/assets/b80c458b-29ea-4790-a640-8fa3b5550610)

### Option 3: local from the source
🔴 Only for advanced users, who are familiar with Python.<br>
Launch the project locally following these steps or watch the [video tutorial](https://youtu.be/OUzCO7SWKyA):

<details>
<summary>Instructions for local version (click to expand)</summary>
*️⃣ This option is DEPRECATED, you will not find the zip archive in the releases anymore. You need to clone the repository and run the script manually.

1. Clone the repository.
2. Install [Python 3.12](https://www.python.org/downloads/release/python-3120/) for your OS.
3. Launch the script to create a virtual environment, install dependencies and run the tool:
    - Windows: right-click on the `run.ps1` and select **Run with PowerShell** (if an error occurs, run `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` in PowerShell)
    - Linux / Mac: execute the `sh run.sh` in a terminal in the tool's folder (this one will work on Windows too, if you have bash installed)
4. Minimalistic GUI will appear.
5. Copy lat and lon from Google Maps and paste them into the corresponding fields. To do this, right-click on someplace on the map and click on the coordinates which look like this: `52.520008, 13.404954`. The first number is the latitude, the second one is the longitude. This point will be the center of the map.
6. Select the size of the map (2048, 4096, 8192 or 16384 meters). The bigger the map, the longer it takes to generate it. Warning: to open huge maps in Giants Editor, you need a powerful PC. I don't recommend generating maps bigger than 8192 meters. By the way, the default map sizes in the Farming Simulator are 2048x2048 meters.
7. Check the advanced settings if you want to change something. I **strongly recommend changing the `max_height` value** to which suits the map better. For more plain-like maps, set it to lower values (e.g. 200). For mountainous maps, set it to higher values (e.g. 800).
8. Click on the **Generate** button.
9. Wait until the map is generated. It may take a while.
10. The map will be saved in the `output` folder in the tool's folder. You can open `output/maps/map/map.i3d` in the Giants Editor to check if everything is ok. If you need to run the script again, start with step 4. The script will delete the previous map and generate a new one.
11. Now you can copy the `output` folder somewhere and start creating your map in the Giants Editor.

</details>

## Settings
Advanced settings are available in the tool's UI under the **Advanced Settings** tab. Here's the list of them:
- `max_height` - the maximum height of the map. The default value is 400. Select smaller values for plain-like maps and bigger values for mountainous maps. You may need to experiment with this value to get the desired result.
- `blur_seed` - the seed for the blur algorithm. The default value is 5, which means 5 meters. The bigger the value, the smoother the map will be. The smaller the value, the more detailed the map will be. Keep in mind that for some regions, where terrain is bumpy, disabling the blur algorithm may lead to a very rough map. So, I recommend leaving this value as it is.

## Info sequence
The script will also generate the `generation_info.json` file in the `output` folder. It contains the following keys: <br>
`"coordinates"` - the coordinates of the map center which you entered,<br>
`"bbox"` - the bounding box of the map in lat and lon,<br>
`"distance"` - the size of the map in meters,<br>
`"minimum_x"` - the minimum x coordinate of the map (UTM projection),<br>
`"minimum_y"` - the minimum y coordinate of the map (UTM projection),<br>
`"maximum_x"` - the maximum x coordinate of the map (UTM projection),<br>
`"maximum_y"` - the maximum y coordinate of the map (UTM projection),<br>
`"height"` - the height of the map in meters (it won't be equal to the distance since the Earth is not flat, sorry flat-earthers),<br>
`"width"` - the width of the map in meters,<br>
`"height_coef"` - since we need a texture of exact size, the height of the map is multiplied by this coefficient,<br>
`"width_coef"` - same as above but for the width,<br>
`"tile_name"` - the name of the SRTM tile which was used to generate the height map, e.g. "N52E013"<br>

You can use this information to adjust some other sources of data to the map, e.g. textures, height maps, etc.

## Bugs and feature requests
If you find a bug or have an idea for a new feature, please create an issue [here](https://github.com/iwatkot/maps4fs/issues) or contact me directly on [Telegram](https://t.me/iwatkot).<br>
ℹ️ Please, don't bother me if the Telegram bot is down. As I said before this is related to the hosting limitations, if you want you can always run the tool locally or support the project by donating, so maybe I'll be able to afford better hosting.
