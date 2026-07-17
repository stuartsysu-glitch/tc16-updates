# TC16 软件更新与下载 / Software Updates and Downloads

TC16 是极低温控温仪的 Windows 控制软件。本仓库提供软件下载页面、在线更新清单和当前公开版本的 Windows 安装程序。

TC16 is the Windows control software for the cryogenic temperature controller. This repository provides the download page, online update manifest, and Windows installers for the currently published versions.

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
- `latest.json`：TC16 软件读取的在线更新清单。
- GitHub Releases：提供当前公开版本的 Windows 安装程序。

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
- `latest.json`: online update manifest used by TC16.
- GitHub Releases: Windows installers for the currently published versions.

### File integrity

The download page displays the installer SHA-256 value for optional integrity verification.

## 维护说明 / Maintenance

每次发布新版本时，应检查 README 中的下载入口、系统要求和升级说明是否仍然准确；仅在相关内容发生变化时更新，避免将“最新版”写成固定版本号或安装包名称。

For every new release, review the download links, system requirements, and update instructions in this README. Update them when the user-facing information changes, and avoid hard-coding the latest version number or installer filename.
