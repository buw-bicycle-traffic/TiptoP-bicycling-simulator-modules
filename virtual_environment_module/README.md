# Virtual Environment Module

This folder contains documentation for setting up and creating virtual environments for the TiptoP bicycling simulator. It covers the full workflow from software installation to building custom scenarios with real-world map data.

---

## 📄 Documentation Overview

> 🚧 **Work in Progress** — This module is still being expanded.

![Status](https://img.shields.io/badge/status-work%20in%20progress-yellow)
![Version](https://img.shields.io/badge/version-1.0-blue)
![University](https://img.shields.io/badge/BUW-Chair%20of%20Bicycle%20Traffic-orange)

The documentation is split across three files, each covering a distinct part of the workflow.

---

### 🖥️ Software
📄 [Software.md](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Software.md)

An introduction to the software stack used in the simulator. It covers CARLA (a branch of Unreal Engine 4 used as the main simulation environment), RoadRunner (for building custom road networks), and the free SUMO/SUMOnity alternative for traffic simulation in Unity. Includes a comparison of both approaches and a list of all tools needed for each workflow.

---

### ⚙️ Computer Setup
📄 [Computer_Setup.md](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Computer_Setup.md)

A step by step [installation guide](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Computer_Setup.md#simulation-software-installation) for building CARLA on Windows, including all dependencies (CMake, Git, Python, Visual Studio 2022, 7-Zip). Also covers the [installation of map making tools](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Computer_Setup.md#map-making-tools-installation) including RoadRunner, Blender with the Blosm add-on, and QGIS.

---

### 🗺️ Setup of Scenarios
📄 [Setup_of_Scenarios.md](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Setup_of_Scenarios.md)

A full walkthrough for creating a custom scenario of a real-world location. Covers [building creation in Blender](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Setup_of_Scenarios.md#using-blender-for-buildings) using the Blosm add-on and OSM data, [road network creation in RoadRunner](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Setup_of_Scenarios.md#road-building) with elevation data, [exporting and importing](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Setup_of_Scenarios.md#importing) into CARLA, and [adding detail](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Setup_of_Scenarios.md#adding-detail-to-scenario) like traffic signs and vegetation. Also includes an [alternative SUMO workflow](https://github.com/buw-bicycle-traffic/TiptoP-bicycling-simulator-modules/blob/main/virtual_environment_module/Setup_of_Scenarios.md#alternative-sumo-scenario-workflow) for those not using CARLA.

---

> 📬 For questions reach out via this repository or at radverkehr@uni-wuppertal.de.