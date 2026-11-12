# PURE Neg platform components v1 / 跨平台除尘组件

**供 OpenRevelare 1.10 及后续兼容版本使用；下载与安装从 1.10 开始提供，1.9.x 及更早版本不支持。**
**For OpenRevelare 1.10 and later compatible versions. Download and installation start with 1.10; versions 1.9.x and earlier are unsupported.**

这是正式组件发行版，供下载站分发可选组件，不代表主程序 1.10 已发布。主程序版本以 [OpenRevelare Releases](https://github.com/Toshihiko-Lin/Open-Revelare/releases) 为准。
This stable component release does not announce an OpenRevelare 1.10 application release.

## 安装 / Installation

导入照片 → 修片 → 除尘 → PURE Neg 下载标识 → 阅读许可 → 选择 GitHub 或 Gitee。安装成功后再次点击 PURE Neg 检测、检查结果并应用修复。
Open a photo, enter the editor, open dust removal, click the PURE Neg download indicator, review notices and choose GitHub or Gitee. After installation, run detection, review and apply repairs.

两侧均提供完整 10 个安装附件。每次安装只下载当前平台所需的四个文件：索引、引擎源码、平台运行库、Node 归档。失败时自动切换另一源；支持取消。无需另装 Node.js、Python、.NET SDK 或编译器。安装器校验大小、SHA-256、原生引擎加载和实际推理，成功后才标记可用。
Both sources host all ten assets. The installer selects four for the current platform, verifies integrity, native loading and inference, and falls back to the other source if needed. No separate development tools are required.

- [GitHub 下载与完整说明](https://github.com/Toshihiko-Lin/openrevelare-models)
- [Gitee 国内下载与完整说明](https://gitee.com/Toshihiko-Lin/openrevelare-models)
- [GitHub 附件](https://github.com/Toshihiko-Lin/openrevelare-models/releases/tag/pureneg-cbcc9fc825ba-v1)
- [Gitee 附件](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/tag/pureneg-cbcc9fc825ba-v1)
- [SHA-256 清单 / Checksums](SHA256SUMS-pureneg-v1.txt)

平台：Windows x64（ONNX/DirectML，CPU 回退）、Linux x64（ONNX CPU，Ubuntu 22.04 ABI）、macOS arm64/x64（CoreML，macOS 14+）。当前不提供 Windows ARM64 或 Linux ARM64 原生包。
Platforms: Windows x64, Linux x64 and macOS arm64/x64, as above. GPU inference does not mean the full pipeline runs on GPU.

附件不是独立安装程序，也不是 Deep-WB 模型；不要放入 `models/`。自动生成的源代码压缩包不含组件。首次安装请通过应用内入口；安装后可以离线使用。
Assets are not standalone installers or Deep-WB models. Auto-generated source archives do not contain the component. Use in-app installation; subsequent use works offline.

## 来源与许可 / Provenance and licenses

PURE Neg 原项目：[easonzhangbin/PURENeg](https://github.com/easonzhangbin/PURENeg)；底层引擎：[magholmes/film-dust](https://github.com/magholmes/film-dust)。欢迎支持原作者与独立客户端。
固定版本：`cbcc9fc825ba9aaf12304c7e9524643995faf4dd`；适配源码：[Toshihiko-Lin/PURENeg](https://github.com/Toshihiko-Lin/PURENeg)。相同训练权重，CoreML/ONNX 一致性检查通过，GPU/CPU 结果不保证逐位相同。

PURE Neg/film-dust: MIT; OpenRevelare model host: GPL-3.0; Node.js/ONNX Runtime/.NET and other dependencies retain their bundled licenses and notices. Preserve included licenses. Deep-WB CC BY-NC-SA 4.0 restrictions apply only to Deep-WB weights.

[Build and validation](https://github.com/Toshihiko-Lin/Open-Revelare/actions/runs/43040694968) · [Corresponding runtime build source](https://github.com/Toshihiko-Lin/Open-Revelare/tree/24862ecbb416d0e19ad5577521f82ebaca2089c7)
