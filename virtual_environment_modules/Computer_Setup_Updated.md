# Computer Setup

Software is the backbone of the bicycle simulator. Of course, basic simulators may not have any display or just record basic outputs, but with today's technology we can create virtual environments and scenarios. There are two primary pieces of software used in virtualization and the creation of the virtual environment: Unity and Unreal Engine. Both have been used in many simulation projects. In this case we recommend Unreal Engine, as there has been more development from other research groups to develop packages useful for developing a simulator and managing things like traffic. There are many versions of Unreal Engine, but we recommend and support the use of a branch called CARLA. This branch was developed for autonomous vehicle simulation, but can be easily adjusted for non-AV vehicle use. Unreal Engine is the backbone of the simulation software, but the provided maps could limit your research and scenarios. To create a new scenario, it is required to use RoadRunner, which is unfortunately a product of Mathworks, but is a great fully fleshed-out software with many capabilities for creating custom maps. Other similar software fall short of the feature sets that RoadRunner provides, such as Truevision.

## Simulation Software Installation

Below is a step-by-step guide of how to build a stable CARLA version on the computer for the bicycle simulator, as the official guide can be sometimes vague on how to build the software. If our guide is unclear, you can find the official build guide [here](https://carla.readthedocs.io/en/latest/build_windows/). Before you get started, make sure to create a GitHub account and get access to the Unreal Engine Source code by following this guide: [Unreal Engine Source Code](https://www.unrealengine.com/en-US/ue-on-github).

:::note
Linking your GitHub account to your Epic Games account is required to access the Unreal Engine source code repository. Follow the instructions at the link above to complete this step before proceeding.
:::

The CARLA build depends on several other applications that need to be installed beforehand. Make sure to follow the provided steps in order and always install the correct versions.

1. **Download and install CMAKE** (version 3.9.0 or higher)

   [Download CMAKE](https://cmake.org/download/)

2. **Download and install Git**

   [Download Git](https://git-scm.com/download/win)

3. **Download and install Chocolatey**, then install Make through PowerShell

   [Installing Chocolatey](https://chocolatey.org/install)

   Once Chocolatey is installed, open PowerShell and type:

   ```
   choco install make
   ```

4. **Download and install 7-Zip**

   Make sure it has access to all users and allow it to unpack all items. It is recommended to install with admin access.

   [Download 7-Zip](https://www.7-zip.org/download.html)

5. **Install Python 3.14.3**

   Make sure to check the box to add Python to the PATH during installation.

   [Download Python 3.14.3](https://www.python.org/downloads/release/python-3143/)

6. Once Python is installed, check if Python and pip are installed by typing the following into the Command Prompt:

   ```
   py -V
   py -m pip -V
   ```

   If an error returns for Python, reinstall it and give it the required PATH so it can be called in the Command Prompt. Alternatively, you can manually add it to the PATH in System Variables.

   If an error returns for pip, type the following into the command line:

   ```
   py get-pip.py
   ```

7. If no error returns, continue to the next step.

8. Next, make sure pip is up to date by typing in the Command Line:

   ```
   py -m pip install --upgrade pip
   ```

9. Install the required pip packages using the command below. You may need to direct pip to the correct folder to find the `pipreq.txt` file:

   ```
   py -m pip install -r pipreq.txt
   ```

   Or with a full path:

   ```
   py -m pip install -r C:/Users/example/downloads/pipreq.txt
   ```

   [Download Pip Requirements Text](https://bicyclesimulator.onrender.com/assets/files/pipreq-c1c9f3104ce74e105ffe94e4366b6eae.txt)

   :::note
   This link may not download the text file directly — you may need to copy the text from the new tab and save it as `pipreq.txt` manually.
   :::

10. Once these packages are installed, validate their installation by typing:

    ```
    py -m pip list
    ```

11. **Install Visual Studio 2022**

    Visual Studio 2019 is no longer recommended as it has known issues with the current build. Please use Visual Studio 2022.

    [Visual Studio Downloads](https://visualstudio.microsoft.com/downloads/)

12. When installing Visual Studio, make sure to also install the following packages via the package manager:
    - **x64 Visual C++ Toolset**
    - **Python tools**
    - **.NET Framework 4.6.2**

13. After installation is complete, also install the **Windows 8.1 SDK** add-on. This is a legacy version required for the CARLA build.

    [Windows SDK Archive — Download Windows 8.1 SDK](https://learn.microsoft.com/en-us/windows/apps/windows-sdk/downloads-archive)

    :::note
    Microsoft notes that this unserviced installer may be susceptible to CVE-2024-29187. Install with awareness of this, as it is required for the CARLA build.
    :::

14. Now with everything installed we can start building Unreal Engine for CARLA.

15. Open Command Prompt.

16. Navigate to the root of your drive. Type:

    ```
    cd C:
    ```

    or type `cd ..` repeatedly until you reach the highest folder of the drive. Then clone the Unreal Engine repository. **Note:** This file is quite large and will take up over 100 GB of space. Make sure your drive has sufficient space before proceeding.

    ```
    git clone --depth 1 -b carla https://github.com/CarlaUnreal/UnrealEngine.git
    ```

17. Once the download is complete, navigate into the downloaded folder:

    ```
    cd UnrealEngine
    ```

18. Run the setup script:

    ```
    Setup.bat
    ```

19. Once Setup.bat is finished, run:

    ```
    GenerateProjectFiles.bat
    ```

20. Once complete, it is time to compile Unreal Engine. Open File Explorer, navigate to the `UnrealEngine` folder, and open the Visual Studio Solution file `UE4.sln`.

21. Once the file is open in Visual Studio, change the build bar so that the following are displayed: **Development Editor**, **Win64**, and **UnrealBuildTool**.

    ![VS Example](https://bicyclesimulator.onrender.com/assets/images/VS_Ex-15d787a98c8883a620bbc41199a11637.png)

22. Right-click on the Solution `UE4` in the Solution Explorer and select **Build**. The build will take some time depending on your hardware.

    ![VS Solution](https://bicyclesimulator.onrender.com/assets/images/VS_Sol-a7046276557174b4d8be9833721bd118.png)

23. Once the build is complete, verify it was successful by navigating to the Unreal Engine folder and launching `UE4Editor`:

    ```
    C:\UnrealEngine\Engine\Binaries\Win64
    ```

24. Add the Unreal Engine path as a system environment variable. Go to **Advanced System Settings → Environment Variables → New**, then add:

    - **Variable name:** `UE4_ROOT`
    - **Variable value:** `C:\UnrealEngine` (or wherever you installed it)

25. Now to build and download CARLA. In Command Prompt, navigate again to the root of your drive:

    ```
    cd C:
    ```

26. Clone the CARLA repository:

    ```
    git clone https://github.com/carla-simulator/carla
    ```

    Or for a specific version (we recommend the most recent):

    ```
    git clone --branch 0.9.XX https://github.com/carla-simulator/carla
    ```

27. Navigate into the CARLA folder:

    ```
    cd carla
    ```

28. Run the update script to download the required assets. This will take some time:

    ```
    Update.bat
    ```

29. Once complete, verify the download and unpacking were successful by checking the command line logs. If not, reinstall 7-Zip with the correct permissions and restart from step 25. Make sure to delete the CARLA folder before restarting.

30. Open the **x64 Native Tools Command Prompt for Visual Studio** (not a regular Command Prompt — this runs through Visual Studio).

31. Navigate to the CARLA folder:

    ```
    cd C:\carla
    ```

32. Build the Python API:

    ```
    make PythonAPI
    ```

33. This will take some time. Once complete, verify there are no error codes and that a `dist` folder was created at `\carla\PythonAPI\carla`. If an error is present, re-run the command from step 31.

34. If errors continue to persist, you will need to start over from step 1. Check that all required software is installed correctly with full admin access. To update all Python packages, run this in PowerShell:

    ```
    .\pip freeze | %{$_.split('==')[0]} | %{pip install --upgrade $_}
    ```

    :::note
    Make sure to include `.\` before `pip` as shown above, otherwise the command may not execute correctly.
    :::

35. If no errors are present, launch CARLA by entering this command in the x64 Command Prompt while in the CARLA folder:

    ```
    make launch
    ```

36. This may take some time to launch Unreal Engine. Once launched, you have successfully built CARLA.

37. We recommend running the included examples to verify everything works. Press Play on the first example world, then open a new Command Prompt, navigate to the examples folder, and run the traffic generation script:

    ```
    cd C:\carla\PythonAPI\examples
    python generate_traffic.py
    ```

38. If you received a critical failure message, you will need to start over from step 1. Make sure to delete the CARLA folder and the UnrealEngine folder before starting over.

---

## Map Making Tools Installation

### RoadRunner

Installation of RoadRunner is straightforward compared to CARLA. To install RoadRunner you will first need a license. Most university institutions are given free licenses, but this may require a purchase. We highly recommend RoadRunner as it is a great and easy way to create roads and maps for 3D environments. Once you have a license and a MathWorks login, you will be able to access the help center, which has a detailed installation guide.

To find the Host ID for your standalone license, use the following command in Command Prompt. Use this ID for the Host ID field and remove the dash from the ID or it will not work.

```
vol c:
```

This should return something like:

```
Volume in drive C is OS
Volume Serial Number is XXXX-XXXX
```

### Blender

For creating building assets, we recommend using Blender, as it is free to use and has many useful features and add-ons.

[Download Blender](https://www.blender.org/download/)

One particularly useful add-on is **Blosm**, which imports OSM data, ArcGIS data, and Google data (including terrain and building data) into Blender. It can generate 3D buildings, roads, and trees that can then be imported into CARLA. This is great for creating a digital copy of a real location, though the detail is limited to the available source data. A premium version is available that adds material textures to buildings.

[Blosm Add-on](https://github.com/vvoovv/blosm)

### QGIS

QGIS is a powerful open-source GIS tool that may be needed for creating custom maps, particularly for obtaining GIS data from OpenStreetMap and transforming elevation data into a format usable by RoadRunner. Many tutorials are available in the QGIS community. When installing, we recommend also downloading the **QuickOSM** plugin, which makes it easy to import OSM data directly into your map.

[Download QGIS](https://www.qgis.org/en/site/forusers/download.html)
