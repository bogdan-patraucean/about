## Frequently asked questions about Wintoys

### Why is the code closed-source?

There are a lot of reasons why open-source might not be the right option for every project. Making a project open-source comes with more responsibility, since you now not only have a project to develop, but a community to manage and more risks to mitigate. You can no longer afford your own pace since people can contribute at any point. Any contribution has the potential of being great or being dangerous, so it has to be reviewed. That's time I don't have. Making your code public means anybody can have a copy, including companies that train their AI models on other people's work, without permission. I refuse to let Microsoft, OpenAI, or any other company steal my work without permission for a profit. On the otherhand, even if no model would be trained on my code, there is still a malicious intent to impersonate me by scamming other people with a copy of my app, and I want to minimize that risk as much as possible. [Chrysalis](https://www.rapid7.com/blog/post/tr-chrysalis-backdoor-dive-into-lotus-blossoms-toolkit/), the backdoor that came with Notepad++ for months, is one of the examples of how things can go wrong if risks are not mitigated. I could continue with other reasons, but I think it's enough to understand why open-source is not the right approach for me.

How do I ensure transparency then? By letting the product and users talk about this. I know it's hard to believe that a product like this is free and there is no catch, but I'm one of those users who understands the frustration of having ads everywhere, the frustration of having your data collected without consent, or the frustration of using products designed to make money, not to address a genuine need. I made a product that I wanted to use myself. It was designed to solve an existing problem, not to invent a new one.

There are still good people in this world.

### How to change the language?

The first language is automatically selected from the list of installed language packs found in Windows settings:_Time & language > Language & region > Language_.
The list can be reordered using drag and drop and if your language is not supported, English is the fallback one.

### How to uninstall?

This is a modern Windows app, it can't be [uninstalled](https://support.microsoft.com/en-us/windows/uninstall-or-remove-apps-and-programs-in-windows-4b55f974-2cc6-2d2b-d092-5905080eaf98#id0ebd=windows_11) from the Control Panel like the old ones, you can either:
- search for the app in the Start menu - right click - uninstall
- search for the app in the Windows settings app - installed apps section - click on the 3-dot menu - uninstall

### Why can't I run the performance benchmark if my laptop is charging?

Windows reports the battery status to the app and it might be the cause that your battery health is poor or discharging even if plugged in. The Windows Experience Index benchmark can't be run while the battery is reported as _discharging_.

### How can I get a 10 score when running the performance benchmark?

The maximum value supported by the assesment tool ([winsat](https://en.wikipedia.org/wiki/Windows_System_Assessment_Tool)) is **9.9**.

### Why is HAGS (hardware-accelerated GPU scheduling) option disabled?

This option is automatically disabled if your GPU does not support it.

### Why is ultimate performance power plan option disabled?

Devices that support [Modern Standby](https://learn.microsoft.com/en-us/windows/win32/power/system-power-states#sleep-state-modern-standby) (S0 power state) can't have multiple power plans.

### Why is the displayed RAM capacity different than the actual capacity?

This is how `WMI` (the tool used by the app to get these kind of information) reports the RAM capacity. Something on your OS is corrupted, might actually be the WMI repository itself. You can try to [rebuild it](https://techcommunity.microsoft.com/t5/ask-the-performance-team/wmi-rebuilding-the-wmi-repository/ba-p/373846) or reinstall your OS as a last, unpleasant solution.

### Why does the text look weird and pixelated in certain apps after tweaking performance settings?

The setting found under _Performance > Visual > Adjust visual effects for best performance_ will make fonts look more pixelated as a side effect. This effect is caused by _Smooth edges of screen fonts_ option, which for best performance needs to be turned off.

### Why are settings not applied when using the app with another logged user?

The app requires administrator rights, so the user opening the app must be an administrator as well, otherwise, despite you being logged in with another user, the app will still open with the administrator user, all settings being applied to that one.
To make a user an administrator you can use `net localgroup` command or `lusrmgr.msc` tool.

### Why is my Windows activation key displayed as BBBBB-BBBBB-BBBBB-BBBBB-BBBBB?

This means you have a [volume](https://learn.microsoft.com/en-us/licensing/products-keys-faq#what-is-volume-activation) license, which is not stored locally on your device, but managed by the organization that owns it.

### How do I get rid of _"Some settings are managed by your organization"_ message from the settings app?

This message appears when certain Windows settings configured in [Group Policies](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)) are changed (either by your organization or by third party apps). You can find a tutorial to get rid of it [here](https://answers.microsoft.com/en-us/windows/forum/windows_10-other_settings/some-of-these-settings-are-hidden-or-managed-by/0f43eb7c-b01b-4615-8cf7-db047ac044aa), but settings affected by this message will reset to their default.

### Why can't I uninstall Microsoft Edge even if I enabled the Digital Markets Act option?

Uninstalling Microsoft Edge [is not supported on LTSC versions of Windows](https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/faq#can-the-edge-browser-be-uninstalled-in-iot-enterprise), with no exception for  EEA, as Edge is considered a "_core_" part of the OS.
