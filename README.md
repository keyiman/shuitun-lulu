# 水豚噜噜

为 Codex Pets 制作的透明背景动画宠物：圆润橙黄色水豚，佩戴河豚造型斜挎包，采用软萌 3D 卡通风格。

本仓库提供最终宠物定义、动画图集和预览动图，不包含完整生成过程，也无需编译。

## 目录结构

```text
shuitun-lulu/
├── .gitignore
├── LICENSE
├── README.md
├── pet.json                 # 宠物定义，默认引用 spritesheet.webp
├── spritesheet.webp         # 默认动画图集
├── spritesheet.png          # 无损备份图集
└── preview/
    ├── idle.gif             # 待机预览
    ├── running-left.gif     # 向左跑预览
    └── running-right.gif    # 向右跑预览
```

两份图集均为 **1536 × 1872 像素**。使用本地宠物定义时，最少需要 `pet.json` 和 `spritesheet.webp`；PNG 与预览目录可选。

## 获取与安装

### 1. 获取文件

在仓库页面选择 **Code → Download ZIP** 并解压，或使用 Git：

```bash
git clone https://github.com/keyiman/shuitun-lulu.git
cd shuitun-lulu
```

### 2. 导入宠物

**支持安装链接的桌面客户端**

打开已启用 Pets 功能的客户端，再点击 [安装水豚噜噜](codex://pets/install?name=%E6%B0%B4%E8%B1%9A%E5%99%9C%E5%99%9C&imageUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fkeyiman%2Fshuitun-lulu%2Fmain%2Fspritesheet.webp)，按客户端提示完成安装。

该链接从本仓库下载 WebP 图集，需要联网；安装链接的参数说明见 [OpenAI 官方文档](https://learn.chatgpt.com/docs/reference/commands#pets)。

**支持本地 `pet.json` 的客户端**

按该客户端的要求，将以下两个文件放在同一个宠物目录中：

```text
<客户端的自定义宠物目录>/
└── shuitun-lulu/
    ├── pet.json
    └── spritesheet.webp
```

`<客户端的自定义宠物目录>` 是占位说明，请替换为客户端实际要求的路径。本仓库未规定统一安装路径。

随后刷新宠物列表，选择“水豚噜噜”；若列表未更新，可重新启动客户端。

**ChatGPT 网页端**

若设置中提供 **Personalization → Pet → Upload pet**，可上传 `spritesheet.webp`，也可使用 `spritesheet.png`。两份文件的尺寸和大小均符合官方列出的上传要求，但实际动画效果仍需在目标客户端确认。参见 [Pets 官方文档](https://learn.chatgpt.com/docs/pets)。

## 预览方式

直接打开 `preview/` 中的 GIF，即可查看部分动画，无需安装宠物：

- [待机](preview/idle.gif)
- [向左跑](preview/running-left.gif)
- [向右跑](preview/running-right.gif)

下载后可用浏览器或支持 GIF 动画的图片查看器打开。`spritesheet.webp` 和 `spritesheet.png` 是整张帧图集，普通图片查看器通常会显示所有帧；实际动画由宠物客户端播放。

## 兼容性提示

- 需要支持自定义宠物及对应图集布局的客户端；能够打开 WebP 图片，不代表能够正确播放宠物动画。
- 仓库未标注最低客户端版本，也未在 `pet.json` 中声明图集格式版本。安装链接采用客户端默认格式，不能据此保证适配所有版本。
- 本地安装时保留文件名与相对路径。当前 `pet.json` 的 `spritesheetPath` 为 `spritesheet.webp`。
- 不要缩放、裁剪或重排图集，否则可能导致帧错位。
- 各端的宠物入口和可用性可能不同，桌面端本地宠物不会自动同步到网页端。开启系统“减少动态效果”时，宠物可能只显示静态帧。参见 [Pets 官方文档](https://learn.chatgpt.com/docs/pets)。

## 常见问题

**安装链接没有反应？**

确认已安装并打开支持该链接的客户端，且 Pets 功能已启用；允许浏览器打开 `codex://` 链接。仍无法打开时，使用目标客户端支持的本地导入或上传方式。

**本地安装后找不到宠物，或图片为空？**

检查安装目录是否正确、是否多套了一层 ZIP 解压目录，以及 `pet.json` 与 `spritesheet.webp` 是否同级；随后刷新列表或重启客户端。

**可以改用 PNG 吗？**

可以尝试，但本地定义不会自动切换。确认客户端支持 PNG 后，将 `pet.json` 中的字段改为：

```json
"spritesheetPath": "spritesheet.png"
```

**动画错位或不播放？**

先确认使用的是原始图集，并检查客户端支持的图集格式；若只显示静态帧，也检查系统的“减少动态效果”设置。预览 GIF 仅供展示，不能替代安装图集。

## 许可证

采用 [MIT License](LICENSE)。使用、修改或再分发时，请保留许可证要求的版权声明与许可声明。
