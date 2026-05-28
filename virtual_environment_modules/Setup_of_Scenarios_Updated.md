# Setup of Scenarios

In this chapter, we will talk about how to set up your own custom scenario of a real world location.

:::note
This chapter covers the full scenario creation workflow for **CARLA**, using RoadRunner for road networks and Blender for buildings. If you are working with the **SUMO/SUMOnity** workflow instead, see the [Alternative: SUMO Scenario Workflow](#alternative-sumo-scenario-workflow) section at the bottom of this page.
:::

## Using Blender for Buildings

To start out creating our custom map, we will start by using Blender to create the buildings. In this tutorial, we will also be using Blosm, so please have that installed before starting. It is also recommended to have the premium version of Blosm to add more realism and building textures.

1. Open Blender and open a blank new project

2. Once open, we will open up Blosm on the side of Blender

![Blender1](https://bicyclesimulator.onrender.com/assets/images/Blender1-9daeb98c2e2e540e183f07b0c5556685.png)

![Blender2](https://bicyclesimulator.onrender.com/assets/images/Blender2-e46594e4e3af944b56df1bd38fa76aa7.png)

3. Now we will select our area of interest using the select button on Blosm, which will open a tab to a map. Here you can select the area you want to create a scenario for. It is recommended that the area be a bit bigger than your interested area, to add more realism and space to your custom map

![Blender3](https://bicyclesimulator.onrender.com/assets/images/Blender3-d5a062909b3c1de9a1bebb4a1579d064.jpg)

4. Once you have your area, copy the selected area using the website instruction on the right side and then paste those coordinates into Blosm with the paste button

![Blender4](https://bicyclesimulator.onrender.com/assets/images/Blender4-c37b002af24aea3643ebeb88c0443000.jpg)

5. Once pasted, you can now add elevation data to your Blender file by using the terrain import function. In the section below the coordinates, you can select terrain and then click on the import button

![Blender5](https://bicyclesimulator.onrender.com/assets/images/Blender5-a0e2df9e070faff08567d672ea4c052c.jpg)

6. Once a gray plane with the terrain data has been imported, you can now add buildings to your file

7. This can be done by going back to the OpenStreetMap tab on Blosm

8. Before you select import, make sure to select Import for Export, Import Buildings, and Relative to Initial Import and then deselect Import as a Single Object and Import Forest

![Blender6](https://bicyclesimulator.onrender.com/assets/images/Blender6-b036b775072ea08100a56bbad8d18bce.jpg)

9. Now import the buildings by clicking import

10. This should have imported your buildings onto the terrain surface

11. Now that you have the buildings for your custom map, you can export these buildings by firstly selecting all the buildings under the Map_XX.osm_buildings

![Blender7](https://bicyclesimulator.onrender.com/assets/images/Blender7-8ca48ad3c5dc95831da6454270bc43f5.png)

12. Then under file, click Export and use FBX to export your file

13. When exporting, select Limit to Selected Objects so that only the buildings are exported

14. Note that CARLA can only handle so many buildings at one time during import. We recommend limiting it to only 1000 buildings per export

15. You now have your buildings for your scenario, which can be imported later

## RoadRunner

Now with the buildings done, we can move to the roads for the custom maps. This section will cover how to start using RoadRunner and what data will be needed. As stated before, RoadRunner is a software which can be used to develop roads for your custom map. The software is robust and can be used to create a very accurate representation of your area's street design, although this does take some time to implement accurately. RoadRunner has functions where it can take map data and transform it into streets, but the results can vary quite greatly, and it is not recommended for streets with complicated or special layouts.

## OSM Data

The first piece of data necessary for creating a custom roadway will be OpenStreetMap (OSM) data. This will be our baseline data. It can be downloaded from OSM easily using the coordinates from Blender to ensure an exact match. If your selected area contains too many objects you may have issues with the export — one solution is to download OSM data through Geofabrik.

[OpenStreetMaps](https://www.openstreetmap.org/)

[Geofabrik Download Server](https://download.geofabrik.de/)

## Elevation Data

To best represent your area of interest, elevation data is important. This data can typically be found through your regional GIS governing body, though availability varies. Some areas do not have this data available, leaving only open-source data which may be lower resolution. The data must be in DEM, IMG, or TIFF format for RoadRunner — vector contour data will need to be converted using QGIS and the TIN interpolation processing tool.

[QGIS Interpolation](https://docs.qgis.org/3.28/en/docs/user_manual/processing_algs/qgis/interpolation.html#tin-interpolation)

[QGIS Interpolation Video](https://www.youtube.com/watch?v=kAvGW0yH6_E&embeds_referring_euri=https%3A%2F%2Fcdn.iframe.ly%2F&source_ve_path=Mjg2NjY&feature=emb_logo)

![QGIS Photo](https://bicyclesimulator.onrender.com/assets/images/QGIS-71c5f7ac69b47599ab55919c7eea3765.png)

In NRW for example, LiDAR contour vector data is available from the state. This can be imported into QGIS, enriched with an Elevation attribute via the field calculator, then processed through the TIN interpolation tool to produce a raster surface. A raster resample interpolation (via GRASS tools) can further smooth the result before exporting in WGS 84 coordinate system.

## Road Building

Now with all the important data for RoadRunner — OSM and topography — we can start creating the custom map.

1. Create a new project in RoadRunner

![Roadrunner1](https://bicyclesimulator.onrender.com/assets/images/RR1-74cb40dd3f55bda768832d311e69b426.jpg)

2. Create a new scene

![Roadrunner2](https://bicyclesimulator.onrender.com/assets/images/RR2-8e4d414d32df5fb3e10408de66af03a8.jpg)

3. Now with a new scene open, we can start creating the map

4. Place the OSM data and topography data into the library browser by dragging the files in. Create a new folder in the library browser to contain all map information by right-clicking on the explorer and going to New → Folder

5. Your files should look like this — one containing the topography data and one containing the OSM data

![Roadrunner3](https://bicyclesimulator.onrender.com/assets/images/RR3-a6996b310b2f0af5549410724d59b5ca.png)

6. Right-click on the topography data and select topography to ensure it is set to the correct default type

![Roadrunner4](https://bicyclesimulator.onrender.com/assets/images/RR4-3b49164e1565dd7c00989c502bf0d04d.jpg)

7. Drag both OSM and topography data into the scene. Press F5 and F7 if the data does not appear automatically

![Roadrunner5](https://bicyclesimulator.onrender.com/assets/images/RR5-10ed4af938ed97d888b3cd73ed1d139a.png)

8. If the OSM map appears too cluttered, remove it and re-add only the road network using the SD Map Viewer Tool

9. Start creating the road network using the road plan tool in the upper left. Right-click to set road control points, left-click to complete the road

10. Add topography to the roads by clicking Project Roads on the left side of the program

![Roadrunner6](https://bicyclesimulator.onrender.com/assets/images/RR6-e0679b2e926449a0a22d253f0614fff1.jpg)

11. If sharp corners appear due to elevation issues at intersections, adjust the road profile in the bottom left. The blue line is terrain elevation, the purple line is the selected road, and the green line is the intersecting road

![Roadrunner7](https://bicyclesimulator.onrender.com/assets/images/RR7_1-db98ded8246120a5014722e1cc913c56.png)

12. Apply a RoadStyle by dragging it from the RoadStyles folder to a road segment. Edit lanes, widths, and directions as needed

![Roadrunner8](https://bicyclesimulator.onrender.com/assets/images/RR8-e8408f1fb3f3495f2b1ad8f28ae5769d.png)

13. Add lanes using the Lane Add tool. Lanes are added outward from the road's center axis. The Lane Form and Lane Carve tools add and subtract from an existing road

![Roadrunner9](https://bicyclesimulator.onrender.com/assets/images/RR9-26bffbc8d9304591149f5e5a1f3b4c66.jpg)

14. Specify lane types from the list on the right side of the program

![Roadrunner10](https://bicyclesimulator.onrender.com/assets/images/RR10-233544f4b09b777b018b21e5b2d172ad.png)

15. Adjust lane widths using the Lane Width tool

![Roadrunner11](https://bicyclesimulator.onrender.com/assets/images/RR11-370991827fbbe678d3181fad2c4af1ef.jpg)

16. Change traffic direction and access restrictions using the Lane tool. Note that when changing a lane type (e.g. driving to bicycle), access restrictions must be set manually — they do not update automatically

17. For special intersections, use the Custom Junction tool

![Roadrunner14](https://bicyclesimulator.onrender.com/assets/images/RR14-2ccf1806b7c16df5c3ec4deb8137b4ed.jpg)

18. Verify intersections using the Maneuver tool. Add or delete maneuvers as needed. Use Rebuild Maneuver Roads to reset an intersection

![Roadrunner15](https://bicyclesimulator.onrender.com/assets/images/RR15-44029c07ae37438924ec523a5c061c91.jpg)

![Roadrunner16](https://bicyclesimulator.onrender.com/assets/images/RR16-eabf3064c7d0a0fef6b63e8642b8b3fa.png)

19. Terrain surfaces are created automatically when road segments form a closed loop, or can be added manually using the Surface tool. Apply GIS elevation data to surfaces using Apply GIS Data

![Roadrunner17](https://bicyclesimulator.onrender.com/assets/images/RR17-8bd2fc11f75b9c76453525cb03f8af1e.jpg)

![Roadrunner18](https://bicyclesimulator.onrender.com/assets/images/RR18-f391e7946acf98efaf662a47866d9222.png)

20. Adjust lane markings using the Lane Marking tool and the markings library

![Roadrunner19](https://bicyclesimulator.onrender.com/assets/images/RR19-6ac0976d32844cb952d905b6656c251e.jpg)

21. Further RoadRunner features are documented in the official RoadRunner documentation

[RoadRunner Documentation](https://de.mathworks.com/login?uri=https%3A%2F%2Fde.mathworks.com%2Fhelp%2Froadrunner%2Findex.html%3Fs_tid%3DCRUX_lftnav&context=behindmwa)

## Exporting

1. Check the network for errors using the OpenDRIVE Export Preview tool. Accept the standard settings and press Export

![RRexport01](https://bicyclesimulator.onrender.com/assets/images/RREX01-05f70afe46ba0c44c952593cbd1eac90.jpg)

2. Fix any errors shown in the output log. Some warnings (e.g. intersections combined due to proximity) can be ignored — others should be addressed

![RRexport02](https://bicyclesimulator.onrender.com/assets/images/RREX02-2af71613f311d8022f20e4e0a7687eff.jpg)

3. Once the preview looks correct, export via File → Export → CARLA Filmbox (.fbx, .xodr, .rrdata.xml)

## Importing

1. Place the exported files into the import folder in the CARLA directory

2. Open an x64 Native Tools Command Prompt and navigate to the CARLA folder:

```
C:
CD carla
```

3. Run the import command:

```
make Import
```

4. If this returns an error, run the Python script directly:

```
cd util\buildtools
import.py
```

5. Once complete, open CARLA:

```
cd ..
cd ..
make launch
```

6. Navigate to Content → map_package in the Content Browser. If map_package is not present, the import failed — close CARLA and retry

7. If imported correctly, the map will be under map_package → Maps. Open the scene folder and double-click the orange level item

![RRexport03](https://bicyclesimulator.onrender.com/assets/images/RREX03-af6ce52546ba13c343d8a652ac85f67d.jpg)

8. Test the import by running the traffic generation script in a separate Command Prompt:

```
C:
CD Carla\pythonapi\examples
generate_traffic.py
```

9. Import buildings from Blender via Content → Carla → Static → [your buildings folder] → Add/Import → Import Asset. Adjust import scale as needed. Limit to 1000 buildings per import batch. Once all buildings are imported, drag them into the level and align their positions and heights

## Adding Detail to Scenario

With the road network and buildings in place, traffic signs, signals, trees, and other details can be added to increase realism.

### Traffic Signage and Signals

Traffic signs and signals can be added using CARLA's prebuilt signage and traffic light functions. Place the object at the desired location and adjust the trigger box accordingly.

[CARLA Traffic Signals and Signage](https://carla.readthedocs.io/en/latest/tuto_M_custom_add_tl/)

### Vegetation

1. Enter foliage mode via the top toolbar

![CARLAVEG01](https://bicyclesimulator.onrender.com/assets/images/CAVEG01-528f6acd6bf91fe1706e91ca6cee6416.jpg)

2. Foliage assets are found under Content → Carla → Static → Vegetation. Drag foliage into the paint tool menu

![CARLAVEG02](https://bicyclesimulator.onrender.com/assets/images/CAVEG02-f1a1489ac750f6fc7c3e5ee498986d00.jpg)

3. Adjust density, spacing, scaling, and other parameters before painting

![CARLAVEG03](https://bicyclesimulator.onrender.com/assets/images/CAVEG03-210ce6a566ba89d37dfec4d2930e7251.jpg)

4. Paint terrain by left-clicking. Use the checkbox on each foliage item to toggle it on and off

![CARLAVEG04](https://bicyclesimulator.onrender.com/assets/images/CAVEG04-59199f6c9e84028dacdd6961ce86afb8.jpg)

5. To prevent foliage painting onto roads or buildings, select the terrain object and change its Mobility from Static to Movable in the Details panel

![CARLAVEG05](https://bicyclesimulator.onrender.com/assets/images/CAVEG05-d885d381342be47a01f9dce967a4095e.jpg)

---

## Alternative: SUMO Scenario Workflow

If using **SUMO/SUMOnity** instead of CARLA, the scenario creation workflow is different and does not require RoadRunner or a high-end GPU.

### Road Network — netedit

SUMO's built-in visual road editor **netedit** is used to draw the road network. It supports:
- Bidirectional lanes and arbitrary road geometry
- Traffic lights with configurable phase timing
- Roundabouts, curved roads, and custom lane types
- Real-world network import via OpenStreetMap

To import a real-world location directly, use **osmWebWizard** (included with SUMO), which generates a complete road network and traffic demand from any area on OpenStreetMap in a few clicks.

### Traffic Demand

Vehicle flows, routes, and departure times are defined in a route file (`.rou.xml`). Vehicles can be configured with different types (car, bicycle, bus, pedestrian) and parameters such as speed, acceleration, and reaction time.

### Terrain and 3D Environment

Since SUMO handles only traffic logic, the 3D visual environment is built separately in Blender and imported into Unity:

1. A Python script reads the SUMO network file (`.net.xml`) and automatically generates a terrain mesh with elevation (from node Z-values) and road surface meshes
2. The result is exported as FBX from Blender and imported into Unity
3. Mesh Colliders are added in Unity so vehicles land on the terrain correctly

Elevation data for the terrain can be obtained from regional GIS sources (same as the CARLA workflow) and applied to SUMO network nodes in netedit.

### Scenario Output

SUMO records all vehicle positions, speeds, slopes, and headings at every timestep via **FCD output** (Floating Car Data), which is enabled with a single line in the scenario config file. This data is ready for statistical analysis without additional processing.

For details on setting up a SUMO/SUMOnity scenario, refer to the project's internal development documentation.
