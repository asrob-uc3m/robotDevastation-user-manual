# Install Robot Devastation - PC (Windows)

First of all, you need a C++ compiler. You can download the latest Visual Studio (Community edition) from the [Microsoft website](https://www.visualstudio.com/downloads/). In order to configure and build VS projects, CMake will be used ([downloads page](https://cmake.org/download/)).

## Download and install YARP binaries

RD software is designed around YARP. In case you installed Visual Studio 2013, you may just download precompiled binaries from the [YARP downloads page](http://www.yarp.it/installation_downloads.html) (select `MSVC12 x86`) and skip to [#Download and install additional dependencies](#download-and-install-additional-dependencies). If not, you'll need to compile ACE and YARP from sources.

## Download and compile ACE from sources

YARP communications rely on [ACE](http://www.cs.wustl.edu/~schmidt/ACE.html). Download the latest *micro* release of ACE from [here](http://download.dre.vanderbilt.edu/), TAO is not required. Follow the instructions at [Building and Installing ACE on Windows with Microsoft Visual Studio](http://www.dre.vanderbilt.edu/~schmidt/DOC_ROOT/ACE/ACE-INSTALL.html#msvc). Remember to select the *Release WIN32* configuration in VS.

## Download and compile YARP from sources

YARP code is hosted on [GitHub](https://github.com/robotology/yarp). You can download the source code by clicking [here](https://github.com/robotology/yarp/archive/master.zip), or clone the repository in your local machine with the help of your preferred Git client.

Now, configure the VS project:
1. Run the CMake GUI application.
2. Point the *Where is the source code* path to the folder where you have decompressed/cloned YARP.
3. Point the *Where to build the binaries* path to a `/build` subfolder of the previous directory.
4. Click on `Configure` and select the corresponding Visual Studio toolset you had installed at the beginning of this guide. If available, don't select the 64-bit option.
5. Provide the path to your ACE build in the corresponding options: `ACE_INCLUDE_DIR` should point to the *ACE_wrappers* directory (unless renamed), and `ACE_ACE_LIBRARY_RELEASE` to *ACE_wrappers/lib/ACE.lib*.
6. Click on `Generate` and `Open project` (if your CMake GUI version provides such button) or browse to the build path and click on the Visual Studio solution (look for the *.sln* extension). If you want to install YARP in the default path (*C:\Program Files (x86)*), you'll need to start Visual Studio with administrator privileges, then click on *File>Open*, browse to the build folder and open the *.sln* file.

In Visual Studio, select the *Release* configuration and compile the solution. To install YARP (not obligatory), compile the *INSTALL* project from the project explorer.

## Download and install additional dependencies

RD depends on the following libraries:
* [SDL 2.0](https://www.libsdl.org/index.php) ([downloads page](https://www.libsdl.org/download-2.0.php), [direct link](https://www.libsdl.org/release/SDL2-devel-2.0.5-VC.zip))
* [SDL_image 2.0](https://www.libsdl.org/projects/SDL_image/) ([download link](https://www.libsdl.org/projects/SDL_image/release/SDL2_image-2.0.1.zip))
* [SDL_mixer 2.0](https://www.libsdl.org/projects/SDL_mixer/) ([download link](https://www.libsdl.org/projects/SDL_mixer/release/SDL2_mixer-2.0.1.zip))
* [SDL_ttf 2.0](https://www.libsdl.org/projects/SDL_ttf/) ([download link](https://www.libsdl.org/projects/SDL_ttf/release/SDL2_ttf-2.0.14.zip))
* [ZBar](http://zbar.sourceforge.net/) ([download link](https://sourceforge.net/projects/zbar/files/zbar/0.10/zbar-0.10-setup.exe/download))

Unzip/install these libraries in the locations of your choice, you'll need these paths later on.

## Compile Robot Devastation

Run CMake GUI and follow points 1 to 3 from [#Download and compile YARP from sources](#download-and-compile-yarp-from-sources) to prepare your RD build in the desired path. Upon pressing `Configure`, CMake will warn you about missing configuration variables pertaining to previously listed project dependencies that you'll need to provide manually so you can proceed further by clicking `Configure` again. This process should be repeated until no more errors are thrown. Open the Visual Studio solution, select the *Release* configuration and compile.

## Set runtime path

Locations of dependent dynamic libraries (files with the *.dll* extension) should be appended to the *PATH* environment variable in order to link them at run time when YARP and the RD programs (as *.exe* files) are launched. This configuration can be set on *Computer>System properties>Advanced system settings>Advanced>Environment Variables*. Alternatively, you may just copy all DLLs and paste them in the same directories the executables are located in.

## Known issues and remarks

ZBar is shipped with an outdated *zlib1.dll* library, a more recent one can be found in the bundles SDL2 comes with. Remember to omit this file when copying all DLLs to the directory where the executables are placed in, or move its location path after SDL2 in the *PATH* environment variable, depending on your preference as explained in the previous section.

In addition, ZBar binaries are compiled for 32-bit architectures. Thus, we did not recommend a 64-bit build in previous steps. If you want to achieve it anyway, you'll have to [download ZBar's sources](http://zbar.sourceforge.net/download.html) and compile from scratch. 
