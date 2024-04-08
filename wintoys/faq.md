### Frequently asked questions about Wintoys:

#### Why is the code closed-source?

- to ensure the most secure and smooth experience by offering availability only through Microsoft Store and winget
- to avoid any copyright issues like fakes/copies, scams, or LLMs scrapping the code
- to be able to offer a payed add-on with extra features for users who want to support my work

#### How to change the language?

The first language is automatically selected from the list of installed language packs found in Windows settings: _Time & language > Language & region > Language_.
The list can be reordered using drag and drop and if your language is not supported, English is the fallback one.

#### Why can't I run the performance benchmark if my laptop is charging?

Windows reports the battery status to the app and it might be the cause that your battery health is poor or discharging even if plugged in. The WEI benchmark can't be run while the battery is reported as _discharging_.

#### Why is HAGS (hardware-accelerated GPU scheduling) disabled for my GPU?

This option is automatically disabled if your GPU does not support it.

#### Why is the displayed RAM capacity different than the actual capacity?

This is how `WMI` (the tool used by the app to get these kind of information) reports the RAM capacity. Something on your OS is corrupted, might actually be the WMI repository itself. You can try to [rebuild it](https://techcommunity.microsoft.com/t5/ask-the-performance-team/wmi-rebuilding-the-wmi-repository/ba-p/373846) or reinstall your OS as a last, unpleasant solution.

#### Why does the text look weird and pixelated in certain apps after tweaking performance settings?

The setting found under _Performance > Visual > Adjust visual effects for best performance_ will make fonts look more pixelated as a side effect. This effect is caused by _Smooth edges of screen fonts_ option, which for best performance needs to be turned off.

#### Why are settings not applied when using the app with another logged user?

The app requires administrator rights, so the user opening the app must be an administrator as well, otherwise, despite you being logged in with another user, the app will still open with the administrator user, all settings being applied to that one.
To make a user an administrator you can use `net localgroup` command or `lusrmgr.msc` tool.

#### Why is my Windows activation key displayed as BBBBB-BBBBB-BBBBB-BBBBB-BBBBB?

This means you have a [volume](https://learn.microsoft.com/en-us/licensing/products-keys-faq#what-is-volume-activation) license, which is not stored locally on your device, but managed by the organization that owns it.
