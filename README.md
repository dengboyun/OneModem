# 📡 OneModem

> **一张 4G 模块，插上 Mac / iPad，立即变成免提电话 + 短信机。** 不刷固件、不改模块出厂设置，纯软件 TCP 语音桥接，双向数据自动协同。

![version](https://img.shields.io/badge/version-v2.0.0-2ea44f?style=for-the-badge)
![macOS](https://img.shields.io/badge/macOS-13%2B-0071e3?style=for-the-badge)
![iPadOS](https://img.shields.io/badge/iPadOS-16.1%2B-0071e3?style=for-the-badge)
![license](https://img.shields.io/badge/license-Freeware-orange?style=for-the-badge)
![platform](https://img.shields.io/badge/platform-Universal%20%7C%20arm64-lightgrey?style=for-the-badge)

---

## ✨ 它做什么

把一张标准 4G 蜂窝模块（QDC507 / MDM9607 / EC200 等）通过 USB-C 插到 Mac 或 iPad，就能：

- 📞 **免提打电话**——用电脑 / 平板自身的麦克风和扬声器，不用插耳机；
- 💬 **收发短信 / 验证码**——验证码置顶大卡片、一键复制；
- 📶 **看信号与运营商**——实时状态栏常驻；
- 🔄 **双端数据协同**——Mac 与 iPad 的短信、通话记录自动双向合并。

> [!NOTE] 软硬解绑
> OneModem 不绑定任何特定硬件厂商。底层固化全功能、前端全面防呆，**无须手动切换模式**。原 DJI 图传模块仅为实测基线之一，任意符合标准的蜂窝模组均可适配。

---

## 🧩 核心能力卡片

| | | |
| :---: | :---: | :---: |
| 🔄 **双向并集同步** | 🎧 **无损声卡语音桥** | 🔔 **锁屏网络唤醒** |
| 短信 / 通话记录只增不减并集合并，墓碑防复活，原子写入不丢数据 | 保留模块出厂 UAC 声卡，纯软件 TCP 7580 PCM（8kHz/16bit/Mono）机身免提，免改动硬件 | 静音音频流 + 系统级 CallKit / Live Activity 保活，锁屏也能可靠接听来电 |

---

## 🖥️ 系统要求

| 平台 | 版本 | 架构 | 安装包 |
| :--- | :--- | :--- | :--- |
| **macOS** | 13.0 Ventura 及以上 | Intel + Apple Silicon 通用（x86_64 + arm64） | `OneModem-Universal.dmg` |
| **iPadOS** | 16.1 及以上 | arm64 | `OneModem.ipa`（未签名中性包） |

另需：一张有效的 SIM 卡、一根支持数据传输的 USB-C 线、模块天线拧紧。

---

## 📥 下载安装

| 平台 | 一键下载 | 说明 |
| :--- | :--- | :--- |
| 🍎 **Mac** | [⬇️ 下载 OneModem-Universal.dmg](https://github.com/dengboyun/OneModem/releases/latest/download/OneModem-Universal.dmg) | 双击挂载 → 拖入「应用程序」→ 打开即用（通用双架构） |
| 📱 **iPad** | [⬇️ 下载 OneModem.ipa](https://github.com/dengboyun/OneModem/releases/latest/download/OneModem.ipa) | 三选一：TrollStore 巨魔直装（永久）/ AltStore·Sideloadly 自签（7 天）/ LiveContainer 侧载 |

> 📖 完整图文教程见仓库内 [`快速上手指南.md`](快速上手指南.md)。
> 🔐 安装前可下载 [`SHA256SUMS.txt`](SHA256SUMS.txt) 校验文件完整性：`shasum -a 256 <文件名>`。

---

## 🛟 一键恢复无人机出厂模式（安全声明）

OneModem **默认不改动模块出厂配置**。当你需要把模块还回无人机、转卖、或配置改乱时，可执行一键还原，让 USB 组合与声卡回到未改造的出厂状态。

> [!WARNING] 执行前必读
> - **还原后 UAC 声卡消失，OneModem 免提能力会暂时失效**，模块回到纯净出厂状态。
> - **务必先备份出厂快照**（`AT+QCFG="usbcfg"?` 与 `ATI` 的返回值），不同模组出厂值不同，切勿照抄其它型号的参数串。
> - 按 [`快速上手指南.md`](快速上手指南.md) 第三步操作；保留快照即可随时用对应值重新激活。
>
> **本项目仅提供软件工具，不对用户自行进行的硬件刷写 / 参数改动操作承担任何连带责任。** 详见 [`LICENSE`](LICENSE)。

---

## 🔐 隐私与安全

- ✅ **不收集**短信 / 通话 / 联系人 / 位置，所有数据只存在你自己的设备本地；
- ✅ 日志手机号自动打码（仅留后 4 位），导出含明文时明确警示；
- ✅ 代码无硬编码 IMEI / 手机号 / Apple ID / 个人路径，通过四维安全审计；
- ✅ 控制接口仅监听本地回环 `127.0.0.1`，不向局域网暴露 AT 调试口。

---

## 📄 许可

本项目为**免费闭源软件**，仅供个人合规学习与非商业场景使用。禁止二次反编译、商业倒卖。详见 [`LICENSE`](LICENSE)。

> OneModem 是由 DJOneHub（历史工程代号）品牌升级而来。技术设计、数据协同规范与发布门禁详见项目知识库。
