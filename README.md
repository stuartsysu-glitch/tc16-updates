# TC16 软件更新与下载 / Software Updates and Downloads

TC16 是极低温控温仪的 Windows 控制软件。本仓库提供软件下载页面、在线更新清单、曲线模板与示例、图文教程和设备固件。

TC16 is the Windows control software for the cryogenic temperature controller. This repository provides the download page, online update manifest, curve templates and examples, illustrated guides, and device firmware.

[软件下载 / Download](https://stuartsysu-glitch.github.io/tc16-updates/) | [版本发布 / Releases](https://github.com/stuartsysu-glitch/tc16-updates/releases)

## 中文

### 下载与安装

- 适用于 Windows 10 / 11 64 位系统。
- 请从下载页面获取最新版 Windows 安装程序。
- 双击运行安装程序，按提示完成安装。
- 无需管理员权限；覆盖安装会保留原有数据和设置。

### 升级说明

- `v3.2.2` 及更早版本：请从下载页面获取最新版并覆盖安装，无需先卸载旧版。
- `v3.2.3-v3.2.4`：默认安装目录可直接使用软件内更新；自定义安装目录请手动覆盖安装最新版。
- `v3.2.5` 及后续版本：默认目录和自定义目录均可在 TC16 右下角点击“更新”完成升级。

### 仓库内容

- `index.html`：软件下载页面。
- `latest.json`：仅供 TC16 软件自动更新使用的 Windows 安装程序清单。
- `resources.json`：网站读取的曲线包、教程和设备固件清单，不参与软件自动更新。
- GitHub Releases：提供 Windows 安装程序、曲线资源、PDF 教程和设备固件。

### 配套下载

- 曲线包包含 4 种通用格式模板，以及 CMN、PT100、RuOx、Cernox 和 TSH 示例。
- 曲线导入教程以 PDF 单独提供，并同时包含在曲线 ZIP 中。
- 固件下载从 SW3.3.31 开始记录，每个固件条目必须明确 SW、HW 和 PCBA 版本。
- 固件升级教程统一适用于 ETH、原生 USB CDC 和 RS232 UART；三种方式只在连接准备和传输耗时上不同。

### 文件校验

下载页面会显示安装程序的 SHA-256。需要时可使用该值核对文件完整性。

## English

### Download and installation

- Supports 64-bit Windows 10 and Windows 11.
- Open the download page to download the latest version of the Windows installer.
- Run the installer and follow the on-screen instructions.
- Administrator privileges are not required. An in-place installation preserves existing data and settings.

### Updates

- `v3.2.2` and earlier: download the latest version from the download page and install it over the existing version. Uninstalling first is not required.
- `v3.2.3-v3.2.4`: in-app updating works from the default installation directory. Custom-path installations must manually install the latest version once.
- `v3.2.5` and later: the **Update** button works from both default and custom installation directories.

### Repository contents

- `index.html`: software download page.
- `latest.json`: Windows installer manifest used exclusively by the TC16 in-app updater.
- `resources.json`: website manifest for curve files, guides, and device firmware. It is independent of software updates.
- GitHub Releases: Windows installers, curve resources, PDF guides, and device firmware.

### Companion downloads

- The curve bundle includes four format templates plus CMN, PT100, RuOx, Cernox, and TSH examples.
- The curve import PDF is available separately and is also included in the ZIP.
- Public firmware history starts at SW3.3.31, with explicit SW, HW, and PCBA compatibility metadata.
- The firmware guide uses one upgrade flow for ETH, native USB CDC, and RS232 UART; only connection setup and transfer duration differ.

### File integrity

The download page displays the installer SHA-256 value for optional integrity verification.

## 维护说明 / Maintenance

每次发布新版本时，应检查 README 中的下载入口、系统要求和升级说明是否仍然准确；仅在相关内容发生变化时更新，避免将“最新版”写成固定版本号或安装包名称。

- `latest.json` 只能保存 TC16 Windows 软件更新信息。不得加入曲线或下位机固件字段。
- 曲线 Release 标签使用 `curves-v<版本>`，当前源文件目录为 `D:\GD_COM\python上位机\curve`。
- 固件 Release 标签使用 `firmware-sw<SW版本>`，当前源文件目录为 `D:\GD_COM\GD_boot_bin\backup`。
- 曲线 ZIP、独立曲线教程 PDF、固件 BIN 和独立固件教程 PDF 发布后，使用真实文件大小和 SHA-256 重新生成 `resources.json`。
- 更新固件时必须同步核对教程中的兼容 HW、PCBA 和软件界面；升级教程不得限定为单一通讯接口。

For every new release, review the download links, system requirements, and update instructions in this README. Update them when the user-facing information changes, and avoid hard-coding the latest version number or installer filename.

- Keep `latest.json` exclusive to TC16 Windows software updates.
- Use `curves-v<version>` for curve releases and `firmware-sw<SW version>` for firmware releases.
- Regenerate `resources.json` from the final ZIP, PDF, and BIN assets so sizes and SHA-256 values match the published files.
