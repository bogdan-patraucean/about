# Wintoys changelog

### v1.3.15.0
* fixed an issue when stopping SYSTEM account owned scheduled tasks (SYSTEM tasks are now skipped)
* fixed an issue when loading corrupted scheduled tasks
* fixed an issue while closing the app

___


### v1.3.12.0
* a service start mode can now be changed even if the service is stopped
* fixed an issue where the Junk Cleaner would not open again after being closed
* fixed an issue when loading the Store apps

___


### v1.3.8.0
* added startup entrance animation for the Home page
* updated some translations and added a missing one
* fixed services not updating correctly after internal or external changes
* fixed not being able to delete a manually added startup app
* fixed a crash caused by double clicking on a dialog button that would sometimes result in trying to open the same dialog twice
* fixed an issue where restoring the window after opening the app maximized would place it into a weird position
* stabilization

___


### v1.3.0.0 (anniversary update)
- added **Memory diagnostic** feature under Health page
- added **Sleeping pill** feature under  Health page
- added **App updates** option under Health page
- added **Windowed mode optimizations** option under Boost/Gaming settings
- added **Watermark** option under Tweaks/Desktop (only for Insider Previews)
- added two new languages: Italian and Polish
- improved the **Junk Cleaner** by:
     - adding missing files from the Disk Cleanup tool (error reports and dump files)
     - adding the ability to display and select browsers individually
     - adding file size and file count for selected items
- the Reboot button is now hidden instead of disabled when a reboot is not required
- improved layout alignment on the Home page and added two missing translations
- updated some border colors to be more visible on dark theme
- changed the benchmark button's icon and the tooltip translation
- changed the progress ring to a progress bar for apps and services changes
- removed process tracing for win32 apps as it was unreliable (the progress will only be displayed for store apps)
- when an app or a service is changing, now the context menu will not be displayed since the options are disabled
- changed the service context menu so that when it can't be stopped, the start mode is disabled

### Stabilization and bug fixes
- fixed an issue where closing the app would throw an exception (the most occuring exception)
- handled startup crash when certain date information was unavailable on Umm Al-Qura calendars
- fixed an issue where extracting spotlight images to a deleted destintion folder would not work
- fixed an issue where uninstalling an app will break updating the list of apps in realtime
- fixed not being able to open the context menu of a selected service
- fixed an issue where hibernation file size percent was displayed as 20% when the default was actually 40%
- handled exceptions when loading apps and startup apps
- handled exception when stopping an unexisting service
- handled exception when loading a benchmark file that's in use
- handled exception when deleting an unexisting file of a startup app
- handled exception of missing service's translations for `Auto` and `System` start modes
- handled exception when turning off Widgets while the registry key is missing
- handled exception when trying to kill a browser for cache cleaning
- handled exception when counting system restore points

### Technical
- upgraded to .NET 8
- updated WinAppSdk to 1.5.2
- removed Mapster

___

### v1.2.35.0
  - fixed regression of Health page crashing on some systems with exotic date time formats
  - fixed dialogs border color when changing OS theme
  - fixed multiple win32 app uninstall errors
  - fixed null reference exception for license channel
  - fixed error when registry key access is denied while loading apps
  - updated to cswin32 0.3.49
  - stabilization

___


### v1.2.25.0

  - handled error for volume licenses
  - updated privacy policy and copyright range
  - fixed registry GetNumber method when passing an invalid number as string
  - updated some translations

___

### v1.2.22.0

- added the top requested feature: localization infrastructure and the following languages
     - Romanian
     - French
     - Turkish
     - Spanish
     - German
 - added new information when hovering over your Windows version on the _Home_ page
     - license status
     - license channel
     - product key
     - UBR (update build revision)
 - improved app startup times by optimizing CPU and GPU usage algorithms
     - the CPU usage now sits under 1% with optimized code on the Home page (previously there were spikes at every 2 seconds with values between 1-3% on a 13th gen i7)
     - querying the GPU usage is now 1.6 times faster
 - HAGS option will now be disabled if not supported by the GPU
 - added setting to place a shortcut of the app on your Desktop
 - added Widgets option under _Tweaks > Desktop_ (only Windows 11)
 - added Account notifications option under _Tweaks > Start menu_
 - added Suggested notifications option under _Tweaks > Ads_
 - added the option to choose a folder for where spotlight images should be extracted (previously extracted images will be kept and new ones will be apended)
 - added support to show percentages based on culture
 - added support to unpin search, task view, widgets and copilot from the taskbar when using the option to unpinn all items
 - added file name validations when adding an app to open at startup (invalid characters and max length)
 - added checks for safe mode when loading apps and warning on Home page
 - added a system restore warning/recommendation on the welcome experience
 - moved Clock with seconds option from _Tweaks > Desktop_ under _Tweaks > System_
 - File Explorer will now be restarted automatically when setting the Classic context menu option
 - improved welcome experience using FlipView and PipsPager
 - better email validation for the Feedback form
 - changed border color of selected services to be the system accent color (for better visibility)
 - changed apps' and services' labels to have rounded corners (for consistency)
 - all tooltip toggles are now consistently displayed on the left when hover over them
 - changed God mode icon
 - updated to Windows App SDK 1.4.3
 - updated to CommunityToolkit 8
 - removed WUApiLib DLL reference
 - removed IWshRuntimeLibrary DLL reference
 - removed WMI dependency for Restart graphics driver option
 - replaced performance counters for network traffic speed
 - replaced performance counters with PerfLib to query the GPU usage
 - issues and bugs:
      - fixed an issue where turning off _Lockscreen fun facts, tips and tricks_ would disable the wallpapers slideshow
      - fixed an issue where remaining orphan apps registry keys would not be removed when trying to uninstall them
      - fixed an issue where expanding the Cleanup section would render the transition with lag
      - fixed an issue where TaskScheduler would throw an error on create folder
      - fixed an issue that would throw an error on some configurations when getting the active power plan
      - fixed an issue that will sometimes not activate the app window when minimized while closing or rebooting your device
      - fixed an issue where the Shortcut Arrow option would not apply due to a race condition
      - fixed an issue where the network statistics would no longer be available while using some VPNs like ExpressVPN
      - fixed an issue where the GPU usage was displayed correctly only for 3D engine tasks
      - fixed an issue showing the wrong GPU on multimonitor setups
      - fixed an issue where the GPU name is not displayed on a VM

___

### v1.1.65.0

- fixed Health page crashing on some systems with "exotic" date time formats
  
___

### v1.1.58.0

  - handled WMI unavailability (a reason for some of the startup crashes)
  - improved spacing across the app
  - clicking Properties on a startup app will now open the Properties dialog much faster
  - fixed benchmark not loading all scores
    
___

### v1.1.55.0

  - Windows Repair
    - changed how results are displayed: a complete list of logs will be displayed instead of a summary, accessible via a button
    - added the percentage on top of the progress bar
    - fixed not enabling Scan and Repair buttons in some cases where internet was reported as disconnected
  - fixed enabling defragmentation when task folder does not exist
  - improved hibernation percent file size format validations
  - replaced powercfg with win32 apis to avoid issues for different languages
  - logging to EventViewer when the service is not available will no longer crash or display an error
  - other stability improvements
    
___

### v1.1.38.0

  - fixed app no longer being displayed when reopened after closing it while minimized
  - fixed tools like Windows Repair not working due to the OS encoding not being found
  - fixed not being able to toggle some startup apps found in the Startup folder
  - fixed error when resetting apps that don't have settings saved locally
  - apps that might not have the Installed Date available are now displayed
  - added Microsoft.VCLibs.140.00.UWPDesktop as a dependency because it might fix some startup crashes
  - added warning for when a startup app that's an antivirus can't be disabled
  - other stability improvements
    
___

### v1.1.32.0

  - added search by family name for store apps
  - removed Create Restore Point button as the feature was not working reliably
  - updated, replaced and removed some unused or legacy packages
  - tools like Windows Repair, Battery Report, System Restore, should now work no matter what language is set in the OS
  - fixed hibernation file size percent input format errors
  - fixed appxmanifest root error for startup apps
  - fixed Drive Optimization by replacing powershell commands with TaskScheduler library
  - fixed Search context menu option (apps, services) for some default browsers not working
  - fixed not launching the app as admin if the user was not an administrator (this was causing a lot of access denied errors)
  - other stability improvements
    
___

### v1.1.16.0

  - rephrased all descriptions to be more clear for both Boost and Health pages
  - added recommendations and details as tooltips over the toggles so you know all the benefits and downsides of those settings
  - added Classic context menu tweak for Windows 11 under Tweaks > Desktop
  - added Taskbar clock seconds tweak for Windows 11 Moment 3 under Tweaks > Desktop
  - added Camera on/off indicator under Tweaks > Privacy
  - added warning when trying to uninstall Microsoft Store and App Installer
  - added Error Reporting to improve app stability under Settings
  - added revision version number for Win32 apps
  - added a warning for when the Ultimate Performance Power Plan is not supported
  - improved About section under Settings
  - improved Autoinstall suggestions by covering more cases (apps should no longer reinstall after Windows updates)
  - trying to safely uninstall Edge no longer works so the option is now disabled
  - fixed VBS not disabling
  - other stability improvements
