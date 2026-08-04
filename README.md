# 奥奇传说手游立绘/海报 Spine 资源库

《奥奇传说手游》立绘与海报 Spine 动画资源合集，供 [奥奇传说手游立绘提取工具](https://github.com/2205094557/aoqi-pet-tool) 远程按需下载使用，也可手动获取用于本地预览与二次开发。

## 目录结构

```
├── lihui_spine/          # 立绘 Spine 动画（727 套）
│   └── <组合ID>/
│       ├── *.skel        # Spine 骨骼数据（binary 格式）
│       ├── *.atlas       # 纹理图集描述
│       └── *.png         # 纹理图集图片
├── haibao_spine/         # 海报 Spine 动画（52 套）
│   └── <组合ID>/         # 结构同上（skel / atlas / png）
├── view_spine/           # 界面视图 Spine 动画
└── index.json            # 全量索引：组合清单 + 各文件大小（下载校验用）
```

一个组合（combo）代表一套可切换的皮肤/姿态，可能包含多层（layer）Spine 动画。

## 使用方法

### 配合立绘提取工具（推荐）

1. 在软件主页「资源来源」选择 **GitHub 仓库**（内置本仓库地址）；
2. 左侧列表会显示全部 779 套立绘，未下载项呈灰色；
3. 点击任意立绘即自动从本仓库下载并预览，下载完成后可导出为 Wallpaper Engine 壁纸。

### 手动获取

进入对应组合目录，下载 `skel + atlas + png` 三件套即可在本地用 Spine 运行时（3.6 版本）渲染。

## index.json 格式

```json
{
  "version": 1,
  "cats": ["haibao_spine", "lihui_spine", "view_spine"],
  "combos": [
    {
      "key": "1046_haibao_jiu",
      "cat": "haibao_spine",
      "cn": "一叶舟轻",
      "py": "haibao_jiu",
      "layers": [
        {
          "name": "1046_haibao_jiu_b",
          "cat": "haibao_spine",
          "skel": "1046_haibao_jiu_b.skel",
          "atlas": "1046_haibao_jiu_b.atlas",
          "png": "1046_haibao_jiu_b.png",
          "skel_type": "binary",
          "files": [["文件名", 字节数], ...]
        }
      ]
    }
  ]
}
```

工具通过 `files` 中的文件大小校验本地缓存是否完整，缺失时自动下载。

## 数据来源与版权

所有资源提取自《奥奇传说》游戏客户端，仅用于个人学习、研究与预览。**版权归游戏官方所有**，请勿用于任何商业用途或二次分发盈利。如官方要求，本仓库相关内容将立即移除。
