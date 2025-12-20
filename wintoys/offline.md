# Offline installation guide

This guide is not for the average user, pay attention to the instructions!

### MSIX

Using an [MSIX](https://learn.microsoft.com/en-us/windows/msix/overview) package format makes the process of installing offline a bit more difficult compared to other methods like the good old MSI installer or a black-box executable, but it comes with a lot of advantages as well:
- a uniform and consistent experience for all applications (classic ones and modern ones)
- automatic cleanup when uninstalling (no residual files left after uninstallation)
- automatic updates (including differential updates)
- certification and security
- transparency regarding required capabilities like accessing the registry or the internet
- unattended installation (a thing showcased in the guide below)


### Offline installation

Make sure your system meets the minimum required version for the app to run: `Windows 10.0.19044.1706`, otherwise you won't be able to install it.

#### 1. Prepare the script

`installer.bat`
```BASH
@echo off

:: ===================================================
:: Change variables (dependency file names)
:: ===================================================

set "APPINSTALLER_RUNTIME=Microsoft.WindowsAppRuntime.1.8.msix"
set "VCLIBS_DESKTOP=Microsoft.VCLibs.140.00_14.0.33519.0_x64__8wekyb3d8bbwe.appx"
set "VCLIBS_UWP=Microsoft.VCLibs.140.00.UWPDesktop_14.0.33728.0_x64__8wekyb3d8bbwe.appx"
set "APPINSTALLER=Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle"
set "WINTOYS_RUNTIME=Microsoft.WindowsAppRuntime.1.7_7000.617.2103.0_x64__8wekyb3d8bbwe.msix"
set "WINTOYS=11413PtruceanBogdan.Wintoys_2.4.12.0_x64__ankwhmsh70gj6.msix"


:: ===================================================
:: Installation of AppInstaller and its dependencies
:: ===================================================


echo Installing dependencies

echo Installing WindowsAppRuntime needed for AppInstaller

powershell -NoProfile -ExecutionPolicy Bypass -Command "Add-AppxPackage -Path '%APPINSTALLER_RUNTIME%'"

echo Installing Desktop C++ framework

powershell -NoProfile -ExecutionPolicy Bypass -Command "Add-AppxPackage -Path '%VCLIBS_DESKTOP%'"
powershell -NoProfile -ExecutionPolicy Bypass -Command "Add-AppxPackage -Path '%VCLIBS_UWP%'"

echo Installing AppInstaller

powershell -NoProfile -ExecutionPolicy Bypass -Command "Add-AppxPackage -Path '%APPINSTALLER%'"


:: ===================================================
:: Installation of Wintoys and its dependencies
:: ===================================================



echo Installing WindowsAppRuntime needed for Wintoys

powershell -NoProfile -ExecutionPolicy Bypass -Command "Add-AppxPackage -Path '%WINTOYS_RUNTIME%'"

echo Installing Wintoys

powershell -NoProfile -ExecutionPolicy Bypass -Command "Add-AppxPackage -Path '%WINTOYS%'"

echo Done

pause
```
- create a new folder where you will add all the needed files
- copy the contents of the script above and save it as a `.bat` file in that folder


#### 2. Prepare AppInstaller and its dependencies

- use this powershell command to check if it's installed:

```
(Get-AppxPackage Microsoft.DesktopAppInstaller).Version
```

- if installed, remove the _Installation of AppInstaller and it's dependencies_ section from the script since it's not needed and skip to step 3, otherwise continue to prepare the AppInstaller


##### AppInstaller dependencies

- download `DesktopAppInstaller_Dependencies.zip` file from [here](https://github.com/microsoft/winget-cli/releases)
  - look for the release with the Latest label, not Pre-release
  - scroll to the Assets section of the release
  - download and extract the zip in the same root folder where you have the script, keeping only the files specific to your architecture (Wintoys is available only for ARM and x64)
 
- update `APPINSTALLER_RUNTIME`, `VCLIBS_DESKTOP` and `VCLIBS_UWP`, with the name of the files, as in the sample script


##### AppInstaller

- download the AppInstaller from [here](https://github.com/microsoft/winget-cli/releases), same source as for the dependencies
   - look for the release with the Latest label, not Pre-release
   - scroll to the Assets section of the release
   - download the `.msixbundle` file and place it in the same folder
- update `APPINSTALLER` variable from the script with the name of the AppInstaller file


#### 3. Prepare Wintoys and its dependencies

##### Wintoys dependencies

- go to [store.rg-adguard.net](https://store.rg-adguard.net/)
- copy and paste the app URL in the search box so it can find results for it: `https://apps.microsoft.com/detail/9P8LTPGCBZXD`
- click on the checkbox
- look for the appropiate `.msix` runtime for your architecture (available only for ARM and x64), download it and place it in the same folder as the rest of the files
- if you see more verions of the runtime, download the most recent one
- update `WINTOYS_RUNTIME` variable from the script with the name of the runtime file

##### Wintoys

- from the same [store.rg-adguard.net](https://store.rg-adguard.net/) page download the Wintoys MSIX for your architecture
- update `WINTOYS` variable from the script with the name of the app package

##### Run the script

- save all the changes to your script
- you can now copy the folder with all the files to another system, and execute the `installer.bat` file that will automatically install everything

#### Observations
- you can edit the .bat file with Notepad
- it was tested using Windows Sandbox, an image that doesn't have any dependency installed, not even the Microsoft Store
- this script might suffer changes as development is moving forward
