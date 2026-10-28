# Sumi

[![GitHub license](https://img.shields.io/github/license/fankes/Sumi?color=blue&style=flat-square)](https://github.com/fankes/Sumi/blob/main/LICENSE)
[![Telegram Channel](https://img.shields.io/badge/channel-Telegram-blue.svg?logo=telegram&style=flat-square)](https://t.me/XiaofangDaily)
[![Telegram](https://img.shields.io/badge/discussion-Telegram-blue.svg?logo=telegram&style=flat-square)](https://t.me/XiaofangInternet)
[![QQ](https://img.shields.io/badge/discussion-QQ-blue.svg?logo=tencent-qq&logoColor=red&style=flat-square)](https://qm.qq.com/cgi-bin/qm/qr?k=dp2h5YhWiga9WWb_Oh7kSHmx01X8I8ii&jump_from=webapi&authKey=Za5CaFP0lk7+Zgsk2KpoBD7sSaYbeXbsDgFjiWelOeH4VSionpxFJ7V0qQBSqvFM)
[![QQ Channel](https://img.shields.io/badge/discussion-QQ%20频道-blue.svg?logo=tencent-qq&logoColor=red&style=flat-square)](https://pd.qq.com/s/44gcy28h)

English | [简体中文](README-zh-CN.md)

Provide standard monochrome notification icons for non-standard Android systems.

## Project Status

This project is WIP (Work In Progress), and no usable installation package is provided yet.

The features and roadmap below are plans only. They may change as development goes on, and the final released version is what counts.

## Origin

This project is a merge of the following two modules:

- [MIUINativeNotifyIcon](https://github.com/fankes/MIUINativeNotifyIcon): Fix the stock notification bar icon function abandoned by the HyperOS/MIUI
  development team
- [ColorOSNotifyIcon](https://github.com/fankes/ColorOSNotifyIcon): Optimize notification icons for ColorOS and adapt to stock notification icon
  specifications

I have to maintain two modules for two systems at the same time. Their core features are almost the same, but their code is separate, so every change
has to be made twice, which is very inconvenient. So I decided to merge and decouple the two projects into a new one.

The new project is no longer named after a single system and no longer targets only one system. It plans to keep the existing features and support
more systems and devices, such as AOSP and AOSP-like systems.

After this project publishes its official release, the two modules above will stop being maintained. A link to this project will be added to them at
that time, and everyone will be recommended to move to this project.

## Design

- Common features such as notification icon replacement and optimization list sync are implemented once in the module core, without depending on any
  specific system
- The differences of each system (for example, where the icons are broken and the system's own special behavior) are handled by separate compatibility
  parts that do not affect each other
- Supporting a new system only needs a new compatibility part, without changing the core or the other systems
- Android systems that are not specifically supported will be handled with native logic as far as possible

## Planned Features

This project focuses only on notification icons. Platform-specific features of the original modules that are unrelated to notification icons (for
example, removing the developer options warning notification and the charging complete notification on ColorOS) will not be added to this project.

### Common Features

- Replace non-standard colored notification icons of apps with the monochrome icons provided by
  [ANIP](https://github.com/BetterAndroid/android-notification-icon-project)
- Enable and override items in the notification icon optimization list, sync the list and update it automatically every day
- Patch unadapted colored notification icons with a placeholder icon
- Send a reminder notification when a newly installed app has no adaptation data
- Adjust the corner radius of icons in the notification panel, and the Material 3 notification icon style
- Enable and export debug logs

### HyperOS/MIUI

- Migrate the existing features of **MIUINativeNotifyIcon**, such as removing the status bar notification icon count limit, adjusting the notification
  icon alpha in the status bar, and replacing the notification icons of the classic style notification panel

### ColorOS

- Migrate the existing features of **ColorOSNotifyIcon**, including the fix for ColorOS 15 and later, which force the icons to be replaced with the colored
  app icons when notification icons are initialized

### AOSP and AOSP-like Systems

- Fix non-standard colored notification icons of third-party apps
- Handle the behavior change in Android 16 that turns the notification icons in the notification panel into app icons

### Other Systems

- Since users have requested them in issues before, **OneUI** and **Flyme** are also being considered, but supporting them requires a matching device
  or an emulator (AVD) of that system, so there is no guaranteed timeline and it will be done when possible

## Roadmap

- [ ] Finish the module core and common features
- [ ] Migrate HyperOS/MIUI support
- [ ] Migrate ColorOS support
- [ ] Support AOSP and AOSP-like systems
- [ ] Publish the first beta version
- [ ] Publish the official release and stop maintaining **MIUINativeNotifyIcon** and **ColorOSNotifyIcon**
- [ ] Support more systems and devices as needed, such as **OneUI** and **Flyme**

## Contribute to the ANIP

The notification icons of this project come from the ANIP project. [Click here](https://github.com/BetterAndroid/android-notification-icon-project)
for details.

## Notes

1. This software is free and developed out of interest, for learning and communication only. If you obtained it from an unofficial channel by paying
   for it, you may have been defrauded, and you are welcome to report suspicious behavior to us.
2. This software is licensed under the **GNU Affero General Public License (AGPL 3.0)**. According to the license:
    1. Any derivative work must use the same AGPLv3 license
    2. The complete source code must be provided when distributing this software or its modified versions
    3. The original copyright notice and license information must be retained
    4. No additional restrictions may be imposed to limit others' free use of this software
3. We encourage free distribution and improvement under the terms of AGPLv3, but please respect the author's attribution and do not impersonate the
   original author

## More Projects

<!--suppress HtmlDeprecatedAttribute -->
<div align="center">
    <h2>Hey, please stay a moment! 👋</h2>
    <h3>If you find this project helpful, take a look at my other projects below!</h3>
    <h3>If these projects help you, consider giving me a follow or a star ⭐️!</h3>
    <h1><a href="https://github.com/fankes/fankes/blob/main/project-promote/README.md">→ Click here to see more of my projects ←</a></h1>
</div>

## License

- [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.html)

```
Copyright (C) 2017 Fankes Studio(qzmmcn@163.com)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```

Copyright © 2017 Fankes Studio(qzmmcn@163.com)