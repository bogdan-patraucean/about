# Wintoys changelog


> ### **2.4.12.8** • Oct 5, 2025 (in certification)

* added app execution alias, now the app can be launched from the command line (the execution alias is also used to create the app shortcut on desktop)
* fixed an issue where apps won't load due to old MSI installers adding unhandled value types in the registry
* fixed an issue that would cause an exception when the device setup region is missing from the registry
* fixed an issue where checking for a service active dependents when trying to stop it would fail due to localization resources not being found
* fixed an issue where the UCPD option would not load because the ucpd service does not exist

  <br>

> ### **v2.4.6.0** (25H2 ready update) • Oct 4, 2025

 - bumped minimum supported application version from 19041.0 to 19044.1706 (this will make sure the OS contains the update that allows the application to run elevated, as 1706 servicing update is required and [MSIX does not yet cover this scenario](https://github.com/microsoft/WindowsAppSDK/issues/5730), (Windows 10 will still be supported despite the fact that official suport is ending this month)
 - improved welcome screen _end presentation_ flow UX (the button will now be easier to spot)
- Storage cleaner improvements:
  - added support for all browser release channels (Beta, Dev, Canary, Nightly, etc.)
  - added label with the free space available on disk C
  - added a lot of new paths to scan for temporary files in the already existing categories like LiveKernelReports folder
  - relocated the tooltip details to be always visible
  - renamed the junk cleaner to storage cleaner, as not everything is junk (icon updated as well)
  - items from the tree that don't occupy space on the disk will no longer be displayed (except for the System category)
  - improved performance of the deletion process
  - added new items:
     - Logs (Windows logs)
     - Others (only apps or services that come packaged with Windows, like Remote Desktop, Widgets, or Nuget, for developers)
  - fixed a bug showing an incorrect number of files deleted in the toast notification
  - fixed bug where the MEMORY.DMP file would not be deleted
  - fixed an issue where scanning would fail due to the root directory not existing 
- New advanced reset/troubleshoot network dialog that's replacing the flushing DNS one, with multiple options:
   - DNS cache
   - Windows socket catalog
   - TCP/IP protocol: 
   - HTTP proxy
   - Firewall rules
   - Network adapters
   - IP adress
- Startup apps:
  - added startup items from the Startup folder execution delay option
  - relocated the list of applications, will be displayed in a content dialog for a better scrolling experience
  - added a default focus on the application name field when opening the dialog to add a new startup app
- DMA improvements and fixes:
  - fixed a bug where DMA status would be incorrectly displayed in certain scenarios like choosing an EEA region during Windows installation setup and then changing it to one outside EEA
  - in EEA countries the DMA option will no longer be displayed since it's on by default
  - added a tooltip detail regarding SFC reverting the effect of DMA
  - added a [FAQ section](https://bogdan-patraucean.github.io/about/wintoys/faq.html#why-cant-i-uninstall-microsoft-edge-even-if-i-enabled-the-digital-markets-act-option) for LTSC  versions of Windows not supporting the uninstallation of Microsoft Edge
- Performance benchmark:
  - updated the performance score icon to be less confusing (the star suggested a 5 star rating system)
  - removed GamingScore as it was hardcoded to 9.9 due to winsat no longer supporting it (the score might drop because of this)
  - added the maximum score legend when hovering over the score (maximum is 9.9, not 10)
- added _num lock on by default_ option under tweaks/system
- added _co-installers_ option under health page
- added _driver updates_ option under health page
- the system model should now display a more reliable value on the home page
- rewritten messages for File Explorer and Microsoft Store dialog options from the cleanup section
- added the total used space of restore points and a backup warning to the system restore dialog from the cleanup section
- when setting the Windows updating mode to manual, notifications will no longer annoy the user, being fully manual
- added application window minimum height and width
- default app size takes scaling into consideration
- added a debounce to all input fields for better validation performance and a better user experience


#### Bug fixes
- gracefully handled access denied error
- fixed _1 is not a supported codepage_ error when trying to run DISM
- fixed crashes when resizing on some scalings
- fixed an issue where multiple ultimate performance power plan entries were created when turning the option on/off in some cases
- fixed an issue where app updates option would no longer work, after a recent Microsoft Store [update](https://www.neowin.net/news/microsoft-no-longer-allows-turning-off-app-updates-in-the-microsoft-store)
- fixed Snipping Key option not reflecting the OS state
- fixed Windowed mode optimization option not reflecting the OS state on a clean system install
- fixed an issue where some options would be displayed as disabled when loaded on the landing page
- fixed some issues where certain apps were missing from the apps page like Remote Desktop Connection (uninstallable starting from Windows 11 version 23H2), Paint (uninstallable starting from Windows 10 22H2 19045.3758), Snipping Tool (uninstallable starting from Windows 10 22H2 19045.3758), NVIDIA HD Audio Driver, etc.
- fixed an issue where apps with major version 0 were not having the version displayed (for example PowerToys with version 0.94.0.0)
- fixed an issue where apps where displayed using the Store display name instead of the system name (for example Files App will now be displayed as Files, Windows Calculator as Calculator)
- fixed an unhandled exception when the store context might not be available on the device
- fixed an issue where a removed profile option will break the compatibility scanning
- fixed showing empty space for the memory frequency on some virtual machines
- potential fix for not terminating Dropbox promotion app

#### Technical
  - upgraded to .NET 9
  - upgraded to Windows App SDK 1.7
  - updated libraries
  - replaced custom titlebar theming with the new native API introduced in 1.7
  - replaced getting UBR (Windows revision version) from registry with native API

  <br>

> ### **v2.0.91.0** • Jun 17, 2025


- improved security of the feedback process
- updated libraries
- fixed an issue where Alt + Tab might make the app freeze
- fixed an unhandled exception when the store context might not be available on the device
- fixed an issue where a removed profile option would break the compatibility scanning
- upgraded .sln to .slnx
- updated translations

  <br>
  
> ### **v2.0.91.0** • Jun 17, 2025


- improved security of the feedback process
- updated libraries
- fixed an issue where Alt + Tab might make the app freeze
- fixed an unhandled exception when the store context might not be available on the device
- fixed an issue where a removed profile option would break the compatibility scanning
- upgraded .sln to .slnx
- updated translations

  <br>
  
> ### **v2.0.81.0** (major update) • Mar 31, 2025

- designed a new **logo**, with colors dinamically adapting to your theme (light or dark); you might have to rebuild the icon's cache for the icon to update everywhere in the system - you can use Wintoys for this: Health section > Icons cache
- revamped the welcome experience (it's now fullscreen and includes a shortcut for system restore)
- added a neat titlebar app icon animation that will play when the app opens
- added system settings restoration: you can now undo all the changes to the state when the app was first opened; even settings changed by the system itself will be detected
- redesigned sorting and filtering dropdowns across all pages and improved their performance
- added storage system property on the Home page, with on-hover details about partitions, disk type, disk interface, disk model and disk serial number
- added uptime system property on the Home page
- system properties such as storage used space or video card driver will update periodically to reflect the system changes in real time
- settings that require an explorer.exe restart will no longer automatically restart it, letting you to choose the right moment; you will be informed that a restart is requierd with the _Action required_ button from the bottom left, which once clicked will offer you the option to restart explorer.exe
- File explorer section changes and improvements:
    - added _Classic interface_ option (on Windows 11)
    - added options to set _Home_ and _Gallery_ items (on Windows 11)
    - changing _Hidden system files and items_ or _File extensions_ options no longer require a refresh of File explorer
    - the toast to reopen File explorer will now only appear if a window is already opened
- added _Digital Markets Act_ option under Tweaks > System; unlocks exclusive features for EEA (European Economic Area), such as being able to uninstall Edge, but only by launching the uninstaller from a Microsoft signed process like Control Panel or the Settings app; this option does not change your region settings, but Microsoft made it work only with country  codes, not region codes; for example, if you live in Bahrain, you'd have to set the Windows region to India
- added _End task_ option under Tweaks > System (on Windows 11)
- added _Home page in settings_ option under Tweaks > Ads (on Windows 11); this will remove the Home page in Windows settings app
- added new _Super-user_ section under Tweaks with the following options:
    - God mode - moved from the System section
    - Developer mode - new
    - User account control - moved from the System section
    - User choice protection driver (UCPD) - new (hidden if the service is completely missing)
- added an option to receive a notification whenever a startup app is enabled (on Windows 11)
- changing _This PC_ and _Recycle Bin_ options no longer require a manual desktop refresh
- changing _Clock with seconds_ option no longer requires an explorer.exe restart on Windows 11
- the displayed video card will now always be the high power one if present (external or dedicated)
- changed validation behavior for all content dialogs due to consistency reasons (now the action button will be disabled until all validation requirements are met)
- replaced error reporting service: AppCenter is being shutdown by Microsoft on 31st of March, so it was replaced by Application Insights
- updated UAC option icon to match the system one
- improved applications size calculation accuracy and sent an email to Gaben to fix Steam not reporting the size of games according to Windows guidelines
- replaced the teaching tip with a tooltip so a click is no longer needed for the information to be displayed (consumes less memory as well)
- the Cleanup section was moved at the top of the page for a more convenient access
- the junk cleaner now supports Opera and Brave browsers, and crash dumps files in the Error reporting category
- added entrance missing animations for apps and services pages (will play when the pages are set as a landing page)
- the option to unpin everything from the taskbar was removed due to the new [UCPD](https://www.reddit.com/r/Windows11/comments/1imcltj/microsoft_added_a_hidden_driver_that_blocks_third/) service that blocks changes to certain registry keys
- the uninstall option will be greyed out for Windows Security, App Installer and Settings app because they can no longer be removed using official Windows APIs
- repair tool logs dialog now has a smaller font for better readability where there's a lot of text
- a native restart API will now be used to restart Windows when a restart is required to apply some settings
- the _Ultimate performance power plan_ option will now be disabled on unsupported devices
- removed _Watermark_ option under Tweaks > Desktop due to Microsoft making it impossible to safely remove it in recent versions of Insider Preview


#### Stabilization and bug fixes

- fixed an issue where the window size was going out of bounds of the screen on smaller resolutions
- fixed a library issue when loading scheduled tasks (noisy scheduled tasks that require a password to be disabled will be ignored due to security reason)
- fixed _Action required_ button not hiding when reverting the wallpaper quality setting to the original value
- fixed an issue where buttons with progress rings were not preserving their space (meaning their size would change to fit the progress ring)
- fixed an issue with system model and manufacturer not being correctly identified on laptops
- fixed an issue where _Delivery optimization_ option was displayed as disabled when _Devices on the internet and my local network option_ was selected in Windows settings app
- fixed an issue where the divider between sections in a tooltip for services would appear when there is no content to separate
- fixed a random infinite loading when uninstalling modern (Store) apps
- fixed not correctly setting Windows update mode when Windows DisplayVersion is not found in the registry
- fixed an issue where the apps page will crash on devices with Umm Al-Quara calendars
- fixed an issue where the apps page might not load due to versioning containing characters
- fixed an annoying refresh button animation when uninstalling an app or changing a service
- fixed not logging all home page errors for system properties in the EventViewer


#### Known issues

- Alt + Tab might make the app freeze; this is a known WinUI 3 bug that has not yet been fixed by Microsoft, you can find more details about the issue [here](https://github.com/microsoft/microsoft-ui-xaml/issues/10213)

#### Technical
- removed Powershell SDK dependency and reduced app size from 65 to 48 MB
- updated packages

<br>

> ### **v1.3.15.0** • Apr 29, 2024


* fixed an issue when stopping SYSTEM account owned scheduled tasks (SYSTEM tasks are now skipped)
* fixed an issue when loading corrupted scheduled tasks
* fixed an issue while closing the app

<br>

> ### **v1.3.12.0** • Apr 27, 2024


* a service start mode can now be changed even if the service is stopped
* fixed an issue where the Junk Cleaner would not open again after being closed
* fixed an issue when loading the Store apps

<br>

> ### **v1.3.8.0** • Apr 25, 2024


* added startup entrance animation for the Home page
* updated some translations and added a missing one
* fixed services not updating correctly after internal or external changes
* fixed not being able to delete a manually added startup app
* fixed a crash caused by double clicking on a dialog button that would sometimes result in trying to open the same dialog twice
* fixed an issue where restoring the window after opening the app maximized would place it into a weird position
* stabilization

<br>

> ### **v1.3.0.0** (anniversary update) • Apr 18, 2024


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

#### Stabilization and bug fixes
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

#### Technical
- upgraded to .NET 8
- updated WinAppSdk to 1.5.2
- removed Mapster

<br>

> ### **v1.2.35.0** • Dec 2, 2023


- fixed regression of Health page crashing on some systems with exotic date time formats
- fixed dialogs border color when changing OS theme
- fixed multiple win32 app uninstall errors
- fixed null reference exception for license channel
- fixed error when registry key access is denied while loading apps
- updated to cswin32 0.3.49
- stabilization

<br>

> ### **v1.2.25.0** • Nov 30, 2023


- handled error for volume licenses
- updated privacy policy and copyright range
- fixed registry GetNumber method when passing an invalid number as string
- updated some translations

<br>

> ### **v1.2.22.0** • Nov 27, 2023


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

<br>

> ### **v1.1.65.0** • Jul 23, 2023


- fixed Health page crashing on some systems with "exotic" date time formats
  
<br>

> ### **v1.1.58.0** • Jul 20, 2023


- handled WMI unavailability (a reason for some of the startup crashes)
- improved spacing across the app
- clicking Properties on a startup app will now open the Properties dialog much faster
- fixed benchmark not loading all scores
    
<br>
 

> ### **v1.1.55.0** • Jul 7, 2023


  - Windows Repair

     - changed how results are displayed: a complete list of logs will be displayed instead of a summary, accessible via a button
     - added the percentage on top of the progress bar
     - fixed not enabling Scan and Repair buttons in some cases where internet was reported as disconnected

  - fixed enabling defragmentation when task folder does not exist
  - improved hibernation percent file size format validations
  - replaced powercfg with win32 apis to avoid issues for different languages
  - logging to EventViewer when the service is not available will no longer crash or display an error
  - other stability improvements
    
<br>

> ### **v1.1.38.0** • Jun 22, 2023


- fixed app no longer being displayed when reopened after closing it while minimized
- fixed tools like Windows Repair not working due to the OS encoding not being found
- fixed not being able to toggle some startup apps found in the Startup folder
- fixed error when resetting apps that don't have settings saved locally
- apps that might not have the Installed Date available are now displayed
- added Microsoft.VCLibs.140.00.UWPDesktop as a dependency because it might fix some startup crashes
- added warning for when a startup app that's an antivirus can't be disabled
- other stability improvements
    
<br>

> ### **v1.1.32.0** • Jun 17, 2023


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
    
<br>

> ### **v1.1.16.0** • May 23, 2023


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

  <br>
 
> ### **v1.0.46.0** (release) • Apr 18, 2023
