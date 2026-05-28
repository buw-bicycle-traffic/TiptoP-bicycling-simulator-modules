# Software

Software is the backbone of the bicycle simulator. Of course, basic simulators may not have any display or just record basic outputs, but with today's technology we can create virtual environments and scenarios. There are two primary pieces of software used in virtualization and the creation of the virtual environment: Unity and Unreal Engine. Both have been used in many simulation projects. In this case we recommend Unreal Engine, as there has been more development from other research groups to develop packages useful for developing a simulator and managing things like traffic. There are many versions of Unreal Engine, but we recommend and support the use of a branch called CARLA. This branch was developed for autonomous vehicle simulation, but can be easily adjusted for non-AV vehicle use. Unreal Engine is the backbone of the simulation software, but the provided maps could limit your research and scenarios. To create a new scenario, it is required to use RoadRunner, which is unfortunately a product of Mathworks, but is a great fully fleshed-out software with many capabilities for creating custom maps. Other similar software fall short of the feature sets that RoadRunner provides, such as Truevision.

## Computer Languages Required

Some Python language skills are required. You can learn some basic Python skills at the link below, although this may not be enough for developing and using the simulator.

[Learn Python](https://www.learnpython.org/)

C++ is also good to have as it is the scripting language of Unreal Engine and will be needed so that features and changes can be added for scenarios. Note that if working with SUMO/SUMOnity (see below), Python alone is sufficient and C++ is not required.

## Simulation Software

### CARLA

As stated before, CARLA is a branch of Unreal Engine 4 and at its current state is unfinished, although at this stage it provides a somewhat ready-to-go virtual environment with weather, traffic, and other useful features. It also has many plugins, including connection to microscopic modelling software like SUMO or PTV VISSIM. Although it has many great features, it is still in an unfinished state, which may cause issues especially during installation. It is recommended to build CARLA on a fairly robust computer, as it is very compute-intensive compared to other software products. It is also important to have some computer literacy with command line and Python to make installation and troubleshooting easier. In the Computer Setup section of this guide you will find a guide on how to best build CARLA.

[Computer Setup](https://bicyclesimulator.onrender.com/docs/Setup_and_Building_of_Simulator/Computer_Setup)

![Carla Setup](https://bicyclesimulator.onrender.com/assets/images/CarlaExample2-86b561b5d2434b413fe931ec30d2db9b.jpg)

### SUMO / SUMOnity

An alternative simulation approach is **SUMO** (Simulation of Urban MObility) combined with **SUMOnity**, a bridge that connects SUMO's traffic simulation to a Unity 3D environment. This combination is particularly suited to research focused on traffic flow, cycling behaviour, and data collection across many automated scenarios.

Key advantages of the SUMO/SUMOnity approach:

- **Free and open source** — SUMO, Python, and Unity Personal are all free to use, making it accessible to students without institutional software licenses
- **Headless batch simulation** — SUMO can run without a graphical interface and up to 1000x faster than real time, enabling large-scale automated data collection
- **Free scenario creation** — road networks can be built using SUMO's built-in netedit editor and OpenStreetMap import tools, without requiring RoadRunner
- **Runs on standard hardware** — unlike CARLA, SUMO does not require a high-end GPU for traffic simulation
- **FCD data output** — built-in Floating Car Data recording captures position, speed, slope, and heading for every vehicle at every timestep

The trade-off is lower visual fidelity compared to CARLA/Unreal Engine, and no native VR support without additional development. For research requiring high-quality immersive visuals or full vehicle physics, CARLA remains the stronger choice.

## Scenario Building Software

### RoadRunner

RoadRunner is the recommended software for creating new maps for CARLA scenarios. It is a well-developed software that is easy to understand and start using. Some knowledge of GIS and how to obtain data from OpenStreetMap (OSM) is helpful for recreating real-world locations with accuracy, though this is not necessary for fictional scenarios. There are other software programs that can be used such as Truevision Designer, but that software is in very early stages and is somewhat difficult to work with. Other software useful for building environments includes Blender, a free and open-source 3D tool well-suited to creating building models.

:::note
RoadRunner requires a paid MathWorks license. Most university institutions can obtain a free academic license. If using the SUMO/SUMOnity workflow instead of CARLA, RoadRunner is not required — road networks can be built entirely with the free tools described above.
:::

![RoadRunner](https://bicyclesimulator.onrender.com/assets/images/RoadrunnerExample-09fd3f71e566631f17a7393f257478cb.jpg)

### Free Alternatives for SUMO-based Workflows

If building scenarios for SUMO rather than CARLA, the following free tools cover the full workflow:

- **netedit** — SUMO's built-in visual road network editor. Supports arbitrary geometry, bidirectional lanes, roundabouts, traffic lights, and custom lane types. Included with every SUMO installation.
- **osmWebWizard** — generates a complete SUMO scenario (road network + traffic) from any area on OpenStreetMap in a few clicks. Also included with SUMO.
- **netconvert** — converts SUMO networks to OpenDRIVE format (.xodr) for use with other simulators if needed.
- **Blender** — used for creating the matching 3D visual environment in Unity, including terrain generation and road mesh creation from SUMO network data.
- **QGIS** — useful for obtaining and processing GIS elevation data for realistic terrain.
