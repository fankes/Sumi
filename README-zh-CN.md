# Sumi (墨)

[![GitHub license](https://img.shields.io/github/license/fankes/Sumi?color=blue&style=flat-square)](https://github.com/fankes/Sumi/blob/main/LICENSE)
[![Telegram Channel](https://img.shields.io/badge/channel-Telegram-blue.svg?logo=telegram&style=flat-square)](https://t.me/XiaofangDaily)
[![Telegram](https://img.shields.io/badge/discussion-Telegram-blue.svg?logo=telegram&style=flat-square)](https://t.me/XiaofangInternet)
[![QQ](https://img.shields.io/badge/discussion-QQ-blue.svg?logo=tencent-qq&logoColor=red&style=flat-square)](https://qm.qq.com/cgi-bin/qm/qr?k=dp2h5YhWiga9WWb_Oh7kSHmx01X8I8ii&jump_from=webapi&authKey=Za5CaFP0lk7+Zgsk2KpoBD7sSaYbeXbsDgFjiWelOeH4VSionpxFJ7V0qQBSqvFM)
[![QQ 频道](https://img.shields.io/badge/discussion-QQ%20频道-blue.svg?logo=tencent-qq&logoColor=red&style=flat-square)](https://pd.qq.com/s/44gcy28h)

[English](README.md) | 简体中文

为不规范的 Android 系统提供规范的单色通知图标。

## 项目状态

此项目目前处于开发阶段 (WIP)，暂不提供任何可用的安装包。

下文中的功能与路线均为计划内容，可能随开发进度调整，最终以正式发布的版本为准。

## 项目由来

此项目由以下两个模块合并而来：

- [MIUINativeNotifyIcon](https://github.com/fankes/MIUINativeNotifyIcon)：修复被 HyperOS/MIUI 开发组丢弃的原生通知图标
- [ColorOSNotifyIcon](https://github.com/fankes/ColorOSNotifyIcon)：为 ColorOS 优化通知图标以及适配原生通知图标规范

由于本人需要同时维护两个系统的两个模块，两者的核心功能基本相同，但代码各自独立，任何改动都需要在两边重复进行，十分不方便，所以决定将两个项目合并并解耦合为一个新项目。

新项目不再以某个系统命名，也不再只面向某个系统，计划在保留原有功能的基础上适配更多系统与设备，例如原生与类原生系统。

在此项目发布正式版本后，上述两个模块将停止维护，届时会在原项目中添加此项目的链接并建议大家转移到此项目。

## 设计思路

- 通知图标的替换、优化名单的同步等通用功能由模块核心统一实现，不依赖任何特定系统
- 每个系统的差异 (例如图标被破坏的位置、系统自身的特殊行为) 由各自独立的兼容部分处理，互不影响
- 适配新的系统只需要增加对应的兼容部分，不需要改动核心与其他系统的实现
- 未单独适配的 Android 系统将尽量使用原生逻辑进行处理

## 计划功能

此项目只专注于通知图标，原有模块中与通知图标无关的平台特化功能 (例如 ColorOS 的移除开发者选项警告通知、移除充电完成通知) 不会被添加到此项目。

### 通用功能

- 使用 [ANIP](https://github.com/BetterAndroid/android-notification-icon-project) 提供的单色图标替换应用不规范的彩色通知图标
- 通知图标优化名单的启用与覆盖，同步列表与每天自动更新
- 未适配的彩色通知图标使用占位符图标进行修补
- 新安装的应用缺少适配数据时发送通知提醒
- 通知栏中的图标边框圆角大小调整与 Material 3 通知图标风格
- 调试日志的开启与导出

### HyperOS/MIUI

- 迁移 **MIUINativeNotifyIcon** 现有的功能，例如解除状态栏通知图标个数限制、调整状态栏中的通知图标透明度、替换经典样式通知栏的通知图标等

### ColorOS

- 迁移 **ColorOSNotifyIcon** 现有的功能，包括修复 ColorOS 15 及之后版本在通知图标初始化阶段将图标强制替换为应用彩色图标的问题

### 原生与类原生系统

- 修复第三方应用不规范的彩色通知图标
- 针对 Android 16 将通知栏中的通知图标改为应用图标的行为变更进行处理

### 其他系统

- 由于此前有用户在 issues 中提出过需求，**OneUI** 与 **Flyme** 也在考虑范围内，但适配需要有对应的设备或系统的模拟器 (AVD)，所以不保证适配时间，随缘进行

## 行进路线

- [ ] 完成模块核心与通用功能
- [ ] 迁移 HyperOS/MIUI 的适配
- [ ] 迁移 ColorOS 的适配
- [ ] 适配原生与类原生系统
- [ ] 发布第一个测试版本
- [ ] 发布正式版本，停止维护 **MIUINativeNotifyIcon** 与 **ColorOSNotifyIcon**
- [ ] 根据需求适配更多系统与设备，例如 **OneUI** 与 **Flyme**

## 为 ANIP 做出贡献

此项目的通知图标来自 ANIP 项目，[点击这里](https://github.com/BetterAndroid/android-notification-icon-project) 前往查看详情。

## 注意事项

1. 本软件免费、由兴趣驱动开发，仅供学习交流使用。如果你是从其他非官方渠道付费获得本软件，可能已遭遇欺诈，欢迎向我们举报可疑行为。
2. 本软件采用 **GNU Affero General Public License (AGPL 3.0)** 许可证。根据该许可证的要求：
    1. 任何衍生作品必须采用相同的 AGPLv3 许可证
    2. 分发本软件或其修改版本时，必须提供完整的源代码
    3. 必须保留原始的版权声明及许可证信息
    4. 不得额外施加限制来限制他人对本软件的自由使用
3. 我们鼓励在遵守 AGPLv3 条款的前提下进行自由传播和改进，但请尊重作者署名权，勿冒用原作者名义

## 更多项目

<!--suppress HtmlDeprecatedAttribute -->
<div align="center">
    <h2>嘿，还请君留步！👋</h2>
    <h3>如果你觉得这个项目能给你提供帮助，不妨继续往下看看我的更多项目吧！</h3>
    <h3>如果这些项目能为你提供帮助，不妨为我点个关注或者 star ⭐️ 吧！</h3>
    <h1><a href="https://github.com/fankes/fankes/blob/main/project-promote/README-zh-CN.md">→ 查看更多关于我的项目，请点击这里 ←</a></h1>
</div>

## 许可证

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

版权所有 © 2017 Fankes Studio(qzmmcn@163.com)