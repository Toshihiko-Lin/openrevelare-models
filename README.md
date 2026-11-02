# OpenRevelare Models

Optional third-party model downloads for OpenRevelare. Default application packages do not include these weights; the ONNX runtime remains bundled.

## Deep-WB v1

- [Model: net_awb.onnx](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/deep-wb-v1/net_awb.onnx)
- [License and attribution notice](https://github.com/Toshihiko-Lin/openrevelare-models/releases/download/deep-wb-v1/DeepWB-NOTICE.txt)
- [Gitee mirror / 国内镜像](https://gitee.com/Toshihiko-Lin/openrevelare-models/releases/tag/deep-wb-v1)

Size: 17,480,341 bytes. SHA-256: `50503B7F6CFB0663EBA0D0D61CBC68E8E93E56581DB3143B203BAB163F7C9F54`.

## Installation / 安装

Click Smart cast correction in OpenRevelare, review the license and install the optional model. Downloads fall back to Gitee when GitHub fails. CLI: `OpenRevelare.Cli --install-deep-wb`.

首次点击「智能色偏修正」后，确认许可即可下载。GitHub 失败时自动尝试 Gitee 国内镜像。

For offline installation, put `net_awb.onnx` in `%LOCALAPPDATA%/OpenRevelare/models/` on Windows or `${XDG_DATA_HOME:-~/.local/share}/OpenRevelare/models/` on Linux/macOS, or in `models/` beside the executable. `OPENREVELARE_DATA_DIR` overrides the user data directory. User-installed models survive upgrades; delete the file to uninstall.

## Source and license / 来源与许可

Deep White-Balance Editing, CVPR 2020. Authors: Mahmoud Afifi, Konstantinos G. Derpanis, Björn Ommer, Michael S. Brown.

Original project: https://github.com/mahmoudnafifi/Deep_White_Balance

**CC BY-NC-SA 4.0**, for non-commercial use. These third-party weights are outside OpenRevelare's GPL-3.0 license. Preserve attribution and license when redistributing; adaptations must use the same license. Keep `DeepWB-NOTICE.txt` with the model.

模型采用 CC BY-NC-SA 4.0 单独许可，仅限非商业用途，不属于 OpenRevelare 的 GPL-3.0 授权范围。

Full license: https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode

ONNX provenance: https://raw.githubusercontent.com/Toshihiko-Lin/Open-Revelare/ff7e379b27614fdad850ae5f09e3e5f26a99f48b/models/net_awb.onnx
