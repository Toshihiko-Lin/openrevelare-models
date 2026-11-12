# OpenRevelare Models

OpenRevelare 可选第三方模型与除尘组件的独立下载仓库。附件与主程序分开发布，按需安装。
Optional third-party models and dust-removal components, distributed separately from the application.

| 功能 / Feature | 组件版本 / Component release | 安装入口 / Installation |
| --- | --- | --- |
| PURE Neg 自动除尘 / dust removal | `pureneg-cbcc9fc825ba-v1` | **OpenRevelare 1.10 起 / starting with 1.10**，修片 → 除尘 → PURE Neg 下载标识 |
| Deep-WB 智能色偏修正 / smart cast correction | `deep-wb-v1` | 智能色偏修正 / Smart cast correction |

## PURE Neg：从 OpenRevelare 1.10 开始提供

**PURE Neg 的下载与安装从 OpenRevelare 1.10 才开始提供，1.9.x 及更早版本不支持。** 本仓库提供正式组件下载；组件发布不代表主程序 1.10 已发布，请以[主程序发行页](https://github.com/Toshihiko-Lin/Open-Revelare/releases)为准。

**PURE Neg download and installation start with OpenRevelare 1.10. Versions 1.9.x and earlier are unsupported.** This stable component release does not announce an OpenRevelare 1.10 application release.

功能来自 [easonzhangbin/PURENeg](https://github.com/easonzhangbin/PURENeg)，底层 [film-dust](https://github.com/magholmes/film-dust) 由 Magnus Holmes 开发。OpenRevelare 集成基础除尘功能；完整独立客户端请访问 PURE Neg 原项目，欢迎支持原作者。
The integration provides basic dust removal. Visit the upstream project for the standalone PURE Neg application.

### 应用内下载安装 / In-app installation

1. 使用 OpenRevelare **1.10 或后续兼容版本**，导入照片并进入「修片」。/ Use **1.10 or a later compatible version**, import a photo and open the editor.
2. 打开「除尘」，点击 PURE Neg 入口旁的下载标识。/ Open dust removal and click the download indicator beside PURE Neg.
3. 阅读来源与许可，选择「从 GitHub 下载」或「从 Gitee 国内镜像下载」。/ Review the notices, then choose GitHub or the Gitee mirror.
4. 等待任务中心完成下载、校验和模型测试。安装后再次点击 PURE Neg 开始检测，检查预览并「应用修复」。/ Wait for download, verification and the inference probe. Once installed, click PURE Neg again to detect, review and apply repairs.

两个平台提供同一版本、相同内容的完整附件。所选源失败、超时或校验不符时，安装器自动尝试另一源；主动取消不会触发重试，可稍后重新安装。无需单独安装 Node.js、Python、.NET SDK 或编译器。首次安装需要联网，安装成功后可离线使用。
Both sources host the complete matching assets. The installer falls back to the other source on download, timeout or integrity failure, and respects cancellation. No separate Node.js, Python, .NET SDK or compiler installation is needed. Initial installation needs network access; subsequent use works offline.

组件保存在用户数据目录，升级应用后保留：Windows 为 `%LOCALAPPDATA%/OpenRevelare/components/`；Linux/macOS 为 `${XDG_DATA_HOME:-~/.local/share}/OpenRevelare/components/`。`OPENREVELARE_DATA_DIR` 可覆盖用户数据根目录。
Components live in the user data directory above and survive application upgrades; `OPENREVELARE_DATA_DIR` overrides the data root.

### 支持的平台 / Supported platforms

| 应用进程架构 / App architecture | 组件包 / Runtime package | 推理 / Inference |
| --- | --- | --- |
| Windows x64 | `pureneg-runtime-win-x64.zip` | ONNX / DirectML；不可用时回退 CPU / CPU fallback |
| macOS Apple Silicon，macOS 14+ | `pureneg-runtime-osx-arm64.zip` | CoreML，系统调度 CPU/GPU/ANE / system scheduling |
| macOS Intel x64，macOS 14+ | `pureneg-runtime-osx-x64.zip` | CoreML |
| Linux x64，Ubuntu 22.04 ABI | `pureneg-runtime-linux-x64.zip` | ONNX / CPU |

按**应用进程架构**选择包；当前不提供 Windows ARM64 或 Linux ARM64 原生组件。CoreML 不保证每次使用 GPU，检测和修复过程也包含 CPU 工作。
Packages follow the **application process architecture**. Native Windows ARM64 and Linux ARM64 packages are not provided. GPU inference does not mean the entire dust-removal pipeline runs on the GPU.

### 手动下载 / Manual downloads

- [GitHub PURE Neg 组件发行页](https://github.com/Toshihiko-Lin/openrevelare-models/releases/tag/pureneg-cbcc9fc825ba-v1)
- [Gitee PURE Neg 组件发行页 / 国内下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/tag/pureneg-cbcc9fc825ba-v1)
- [全部 10 个安装附件的 SHA-256 / Checksums](SHA256SUMS-pureneg-v1.txt)

| 附件 / Asset | GitHub | Gitee |
| --- | --- | --- |
| `components.json` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/components.json) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/components.json) |
| `engine-sources.zip` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/engine-sources.zip) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/engine-sources.zip) |
| `node-v24.14.1-darwin-arm64.tar.gz` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/node-v24.14.1-darwin-arm64.tar.gz) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/node-v24.14.1-darwin-arm64.tar.gz) |
| `node-v24.14.1-darwin-x64.tar.gz` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/node-v24.14.1-darwin-x64.tar.gz) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/node-v24.14.1-darwin-x64.tar.gz) |
| `node-v24.14.1-linux-x64.tar.gz` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/node-v24.14.1-linux-x64.tar.gz) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/node-v24.14.1-linux-x64.tar.gz) |
| `node-v24.14.1-win-x64.zip` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/node-v24.14.1-win-x64.zip) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/node-v24.14.1-win-x64.zip) |
| `pureneg-runtime-linux-x64.zip` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/pureneg-runtime-linux-x64.zip) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/pureneg-runtime-linux-x64.zip) |
| `pureneg-runtime-osx-arm64.zip` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/pureneg-runtime-osx-arm64.zip) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/pureneg-runtime-osx-arm64.zip) |
| `pureneg-runtime-osx-x64.zip` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/pureneg-runtime-osx-x64.zip) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/pureneg-runtime-osx-x64.zip) |
| `pureneg-runtime-win-x64.zip` | [下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/pureneg-runtime-win-x64.zip) | [下载](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/pureneg-cbcc9fc825ba-v1/pureneg-runtime-win-x64.zip) |


每次安装需要四个附件：`components.json`、`engine-sources.zip`、一个 `pureneg-runtime-*.zip` 和匹配的 `node-v24.14.1-*`。macOS 的 Node 文件使用 `darwin-*` 命名。推荐由应用自动选择、校验和安装。
Each installation uses four assets: the index, engine sources, one platform runtime and the matching Node archive. macOS Node filenames use `darwin-*`.

这些归档**不是独立软件安装程序**。平台自动生成的「源代码 zip/tar.gz」不包含组件。不要把单个运行库 ZIP 或模型放进 Deep-WB 的 `models/` 目录；当前没有通过 GUI 导入这些离线归档的入口。手动下载可用于备份或核对，正常安装使用上方应用内流程。
These archives are **not standalone installers**. Auto-generated source archives do not contain the component. Do not put a runtime ZIP into Deep-WB's `models/` folder. The app currently has no GUI import for offline archives; use the in-app installer for normal setup.

校验示例 / Checksum examples：

```powershell
Get-FileHash .\pureneg-runtime-win-x64.zip -Algorithm SHA256
```

```bash
# Put all ten assets and the checksum file in the same directory
sha256sum -c SHA256SUMS-pureneg-v1.txt  # Linux
shasum -a 256 -c SHA256SUMS-pureneg-v1.txt  # macOS
```

### 常见问题 / Troubleshooting

- **没有入口**：确认主程序为 1.10 或后续兼容版本，并已打开照片。组件附件不能给 1.9.x 添加该功能。/ No entry: check the app version and open a photo; assets cannot add this feature to 1.9.x.
- **下载失败**：在安装对话框改选另一源，检查网络、代理和用户数据目录写入权限，再重试。不要混用不同标签的附件。/ Download failure: select the other source, check network/proxy and data-directory permissions, then retry. Keep assets from the same release together.
- **模型测试失败**：安装器会校验大小和 SHA-256、加载原生引擎并执行真实推理；测试失败不会标记为已安装。确认平台受支持，检查显卡驱动和系统兼容性。/ Setup is marked complete only after integrity, native loading and inference checks pass. Check platform compatibility and drivers if the probe fails.

### 来源与许可 / Provenance and licenses

固定 PURE Neg 版本 / Pinned revision：`cbcc9fc825ba9aaf12304c7e9524643995faf4dd`，来源为 [OpenRevelare 适配分支](https://github.com/Toshihiko-Lin/PURENeg) 与上述原项目。FibreNet 使用相同训练权重，Windows/Linux 以 ONNX 执行，macOS 以 CoreML 执行。[构建与跨格式一致性验证](https://github.com/Toshihiko-Lin/Open-Revelare/actions/runs/43040694968)。

PURE Neg 和 film-dust 采用 **MIT**；OpenRevelare 模型宿主采用 **GPL-3.0**；Node.js、ONNX Runtime、.NET 和其他依赖保留各自许可证与第三方声明，随组件分发。请保留归档中的许可和署名。Deep-WB 的 **CC BY-NC-SA 4.0** 限制只适用于 Deep-WB 权重，不套用于整个仓库或 PURE Neg。
PURE Neg and film-dust are MIT-licensed; the OpenRevelare model host is GPL-3.0. Bundled runtimes retain their own licenses and notices. Preserve the licenses shipped in the archives. Deep-WB's non-commercial license applies specifically to its weights.

---

## Deep-WB v1

- [下载模型 net_awb.onnx](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/deep-wb-v1/net_awb.onnx)
- [下载独立许可声明 DeepWB-NOTICE.txt](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/download/deep-wb-v1/DeepWB-NOTICE.txt)
- [发行版说明](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/tag/deep-wb-v1)
- [GitHub 模型下载](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/deep-wb-v1/net_awb.onnx) · [GitHub 许可声明](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/deep-wb-v1/DeepWB-NOTICE.txt) · [GitHub 发行版说明](https://github.com/Toshihiko-Lin/openrevelare-models/releases/tag/deep-wb-v1)

文件大小：17,480,341 字节（约 17.5 MB）。
SHA-256：`50503B7F6CFB0663EBA0D0D61CBC68E8E93E56581DB3143B203BAB163F7C9F54`

### Deep-WB 安装

首次点击 OpenRevelare「智能色偏修正」时，确认许可后按需下载。默认程序安装包不含模型权重，ONNX 推理运行库仍随程序提供。GitHub 下载失败时自动尝试 Gitee 国内镜像。

离线安装：将 net_awb.onnx 放入 Windows 的 `%LOCALAPPDATA%/OpenRevelare/models/`，Linux/macOS 的 `${XDG_DATA_HOME:-~/.local/share}/OpenRevelare/models/`，或可执行文件旁的 `models/`。`OPENREVELARE_DATA_DIR` 可覆盖用户数据目录。用户目录中的模型升级后保留，删除该文件即可卸载。

CLI：`OpenRevelare.Cli --install-deep-wb`。

### Deep-WB 来源与许可

Deep White-Balance Editing，CVPR 2020。作者：Mahmoud Afifi、Konstantinos G. Derpanis、Björn Ommer、Michael S. Brown。

原项目：https://github.com/mahmoudnafifi/Deep_White_Balance

权重采用 **CC BY-NC-SA 4.0** 单独许可，仅限非商业用途；不属于 OpenRevelare 代码的 GPL-3.0 授权范围。再分发须保留署名与许可，修改后的衍生物须以相同许可发布。请阅读并随模型保留 DeepWB-NOTICE.txt。

许可全文：https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode

原 ONNX 文件：https://raw.githubusercontent.com/Toshihiko-Lin/Open-Revelare/ff7e379b27614fdad850ae5f09e3e5f26a99f48b/models/net_awb.onnx

### Deep-WB installation and license (English)

Click Smart cast correction, review the license and install. GitHub failures fall back to Gitee. CLI: `OpenRevelare.Cli --install-deep-wb`. For offline setup, place `net_awb.onnx` in the `models/` directory documented above (or beside the executable); keep `DeepWB-NOTICE.txt` with the model. Deep-WB weights are licensed under **CC BY-NC-SA 4.0**, for non-commercial use, separately from the GPL-3.0 application. Preserve attribution and the license; adaptations must use the same license. The ONNX runtime for Deep-WB remains bundled with the application.
