# TC16 软件更新与下载 / Software Updates and Downloads

TC16 是极低温控温仪的 Windows 控制软件。本仓库用于提供软件下载页面、在线更新清单和历史版本。

TC16 is the Windows control software for the cryogenic temperature controller. This repository hosts the download page, update manifest, and previous releases.

[软件下载 / Download](https://stuartsysu-glitch.github.io/tc16-updates/) | [历史版本 / Previous releases](https://github.com/stuartsysu-glitch/tc16-updates/releases)

## 中文

### 下载与安装

- 适用于 Windows 10 / 11 64 位系统。
- 请从下载页面获取最新版 Windows 安装程序。
- 双击运行安装程序，按提示完成安装。
- 无需管理员权限；覆盖安装会保留原有数据和设置。

### 升级说明

- `v3.2.3` 及更早版本：请从下载页面获取最新版并覆盖安装，无需先卸载旧版。
- `v3.2.4` 及后续版本：可在 TC16 右下角点击“更新”完成后续升级。

### 仓库内容

- `index.html`：软件下载页面。
- `latest.json`：TC16 软件读取的在线更新清单。
- GitHub Releases：保存各版本的 Windows 安装程序。

### 文件校验

下载页面会显示安装程序的 SHA-256。需要时可使用该值核对文件完整性。

## English

### Download and installation

- Supports 64-bit Windows 10 and Windows 11.
- Open the download page to download the latest version of the Windows installer.
- Run the installer and follow the on-screen instructions.
- Administrator privileges are not required. An in-place installation preserves existing data and settings.

### Updates

- `v3.2.3` and earlier: download the latest version from the download page and install it over the existing version. Uninstalling first is not required.
- `v3.2.4` and later: use the **Update** button in the lower-right corner of TC16 for future updates.

### Repository contents

- `index.html`: software download page.
- `latest.json`: online update manifest used by TC16.
- GitHub Releases: Windows installers for published versions.

### File integrity

The download page displays the installer SHA-256 value for optional integrity verification.

## 维护说明 / Maintenance

每次发布新版本时，应检查 README 中的下载入口、系统要求和升级说明是否仍然准确；仅在相关内容发生变化时更新，避免将“最新版”写成固定版本号或安装包名称。

For every new release, review the download links, system requirements, and update instructions in this README. Update them when the user-facing information changes, and avoid hard-coding the latest version number or installer filename.
