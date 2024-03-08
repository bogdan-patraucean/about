### Frequently asked questions about Wintoys:

#### Why is the app closed-source?

- to ensure the most secure and smooth experience by offering availability only through Microsoft Store and winget
- to avoid any copyright issues like fakes/copies, scams, or LLMs scrapping the code
- to be able to offer a payed add-on with extra features for users who want to support my work


#### How to change the language?

The language is automatically set based on your Windows settings: _Time & language > Language & region > Windows display language_. 
If your language is not supported, English is the fallback language.

#### Why can't I run the performance benchmark if my laptop is charging?

Windows reports the battery status to the app and it might be the cause that your battery health is poor or discharging even if plugged in. The WEI benchmark can't be run while the battery is reported as _discharging_.

#### Why is HAGS (hardware-accelerated GPU scheduling) disabled for my GPU?

This option is automatically disabled if your GPU does not support it.

#### Why is the displayed RAM capacity different than the actual capacity?

This is how WMI (the tool used by the app to get these kind of information) reports the RAM capacity. Something on your OS is corrupted, might actually be the WMI repository itself. You can try to [rebuild it](https://techcommunity.microsoft.com/t5/ask-the-performance-team/wmi-rebuilding-the-wmi-repository/ba-p/373846) or reinstall your OS as a last, unpleasant solution.

#### Why does the text look weird and pixelated in certain apps after tweaking performance settings?

The setting found under _Performance > Visual > Adjust visual effects for best performance_ will make fonts look more pixelated as a side effect. This effect is caused by _Smooth edges of screen fonts_ option, which for best performance needs to be turned off.
