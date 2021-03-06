# Compiling OpenInfraPlatform 

Guide on how to compile the project TUM OpenInfraPlatform.

*Warning:* This document is only a snapshot of the current state (July 2020) and may become obsolete in the future.

## Content 

1. [Prerequisites](#Prerequisites)
2. [Preparing solution](#Setup) 
	* [Download source code](#Source_code)
	* [Generating solution](#Prep_solution) 
3. [Building the OpenInfraPlatform in Visual Studio](#Building_OIP) 
	* [First time](#FirstTime)
	* [Generating IFC early binding](#generating_EarlyBinding)
	* [Compiling user interface](#Compiling_interface)
4. [Generating documentation](#Generating_Doc)
	* [Get Dot and Doxygen](#Get_Dot)
    * [Customizing the build](#Doxy_settings)
    * [Building](#Build_documentation)

## <a name="Prerequisites"></a> Prerequisites 

These steps need to be completed before you can proceed with compiling OIP.

*NOTE:* The OIP only works with the versions listed. No guarranty is given for other versions.

1. **Visual Studio 2017** is installed to your computer - find [here](https://my.visualstudio.com/Downloads?q=visual%20studio%202017&wt.mc_id=o~msft~vscom~older-downloads).
2. **CMake 3.17.0** is installed - find [here](https://cmake.org/download/).
3. **Qt 5.12.1** is installed and included in PATH (environment variable) - find [here](https://www.qt.io/download-open-source).

	*	Download Qt Online Installer 
	*	While your computer is downloading Qt installer, create Qt account. 
	*	Sign in with your new account to Qt installer and select directory, where Qt will be installed (`C:\Qt` should be default option).
	*	Select components to install:

		* Check the *Archive* box
		* Click *Filter*
		* Open section **Qt 5.12.1**
		* **Mandatory:** Select *binaries x64 msvc2017*
		* **Mandatory:** Select *mingw*
		
		![](./fig/Qt_Installation_settings.png)

		* *HINT:* There are components, which Qt Online Installer selects as default options. You can uncheck these components for saving computer memory.

4. **Boost 1_65_1** is installed - find [here](https://sourceforge.net/projects/boost/files/boost-binaries/1.65.1/boost_1_65_1-msvc-14.1-64.exe/download).

	* Create a folder named thirdparty in `C:\` and install **Boost 1_65_1** to `C:\thirdparty\vs2017\x64\boost_1_65_1`.
	* Add this path to the environment variables. (Create new environment variable called `Boost_INCLUDE_DIR`. This variable should point to the binary folder, where **Boost 1_65_1** is staged (e.g. `C:\thirdparty\vs2017\x64\boost_1_65_1`).

5. **Anaconda 2** (version with Python 2.7) - find [here](https://repo.anaconda.com/archive/Anaconda2-2019.10-Windows-x86_64.exe). 


## <a name="Setup"></a> Setup

### <a name="Source_code"></a> Download source code 

 Fork & clone [Open-Infra-Platform repository](https://www.github.com/tumcms/Open-Infra-Platform) - for detailed instuctions consult our [Git Guideline](./GitProcess.md).

### <a name="Prep_solution"></a> Preparing solution 

1. Open CMake.
2. In the line *Where is the source code:* input the path to your clone's source folder (e.g. `C:\dev\Open-Infra-Platform`).
3. In the line *Where to build the binaries:*  input the path to the binaries folder (e.g. `C:\dev\build\Open-Infra-Platform`). 

*NOTE:* The source folder as well as *Program Files* and *Windows* folders are **invalid** locations for the binary folder.

4. Check the *Grouped* and *Advanced* boxes (top right in CMake GUI).
5. Click *Configure*. 
6. Select the Generator:
	* Select *Visual Studio 15 2017 Win64*.
	* Select *x64*
	* Write *host=x64* as optional toolset.

![](./fig/CMake_Installation_settings.png)

7. For detailed descriptions of all configuration options that can be selected in the CMake GUI, consult [CMake options documentation](./CMakeOptions.md).

*HINT:* A few (red) warnings in the lower window of CMake can be ignored as long as it states *Configuring done* at the end.

8. After configuration process has successfully finished, click *Generate*.
9. After generation process is done click *Open Project*. It will open the OpenInfraPlatform solution in Visual Studio.


## <a name="Building_OIP"></a> Building the OpenInfraPlatform in Visual Studio 

### <a name="FirstTime"></a> First Time

When compiling OpenInfraPlatform for the first time, these projects should first be built.

* Execute **Get_OKLABI.cmd** in the source folder -> external (e.g. `C:\dev\Open-Infra-Platform\external`) 
  to prevent an error during the build process. 
  After the execution of **Get_OKLABI.cmd**, it's necessary to *configure* and *generate* OpenInfraPlatform project once again in CMake.

* In the *project browser* open *OpenInfraPlatform* project folder. 
  In the folder *Commands* build  **OpenInfraPlatform.Commands.UpdateBoostMpl**.

* Build all projects within the *Copy* project folder. 

*NOTE:* This only needs to happen when compiling for the first time, or after a deletion of the binaries folder.

### <a name="generating_EarlyBinding"></a> Generating IFC early binding libraries

*NOTE:* If you are using OpenInfraPlatform only with point clouds, you can skip these steps.

1. Find the folder *ExpressBindingGenerator*. Build project **OpenInfraPlatform.ExpressBindingGenerator**.

2. In the folder *ExpressBindingGenerator* find the folder *Commands*. 
   There you should build project **Commands.GenerateEarlyBinding.IFC?** where *?* stands for the chosen IFC version.

	*NOTE:* By default settings, this will build **Commands.GenerateEarlyBinding.IFC4X3_RC1**. 
    If you want to change the schema to another, you need to select the corresponding option in CMake and *generate* in CMake again.

3. **Important**: Now open CMake and select *Generate* to include newly generated IFC early binding code in the solution.

4. Find the folder *EarlyBinding*. Build project **OpenInfraPlatform.IFC?**.

### <a name="Compiling_interface"></a> Compiling user interface

*NOTE:* Build dependencies are set through CMake, so building only the last step should automatically build all.

1. If you are using point clouds *build* project **OpenInfraPlatform.PointCloudProcessing**.
1. *Build* project **OpenInfraPlatform.Core**.
1. *Build* project **OpenInfraPlatform.Rendering**.
1. *Build* project **OpenInfraPlatform.UI**.


## <a name="Generating_Doc"></a> Generating documentation

### <a name="Get_Dot"></a> Get Dot and Doxygen

1. Navigate to folder *external* within OpenInfraPlatform source folder. 
2. Execute:
	* GetDot.cmd  
	* GetDoxygen.cmd

*NOTE:* Read more about Doxygen in our [guidelines](./DoxygenHelp.md).

### <a name="Doxy_settings"></a> Customizing generation

Please consult our [CMake options documentation](./CMakeOptions.md).

### <a name="Build_documentation"></a> Generating documentation

Build the project **OpenInfraPlatform.GenerateDocumentation** within *Commands* folder in the solution.

