### Frequently asked questions about Wintoys:

#### How to change the language?

The language is automatically set based on your Windows settings: _Time & language > Language & region > Windows display language_. 
If your language is not supported, English is the fallback language.

#### Why can't I run the performance benchmark if my laptop is charging?

Windows reports the battery status to the app and it might be the cause that your battery health is poor or discharging even if plugged in. The WEI benchmark can't be run while the battery is reported as _discharging_.

#### Why is HAGS (hardware-accelerated GPU scheduling) disabled for my GPU?

This option is automatically disabled if your GPU does not support it.

#### Why is the displayed RAM capacity different than the actual capacity?

This is how WMI (the tool used by the app to get these kind of information) reports the RAM capacity. Something on your OS is corrupted, might actually be the WMI repository itself. You can try to [rebuild it](https://techcommunity.microsoft.com/t5/ask-the-performance-team/wmi-rebuilding-the-wmi-repository/ba-p/373846) or reinstall your OS as a last, unpleasant solution.
