# dsh-xiaoxin-skin · 蜡笔小新皮肤

DeepSeek Harness Web GUI 的蜡笔小新主题皮肤：春日部街道/夜景双背景（可切换）、红金界面覆盖层、Q 版小新与风间侧栏、四角装饰输入框。

基于 [dsh-deep-whale](https://github.com/Small-tailqwq/dsh-deep-whale) 的 `maid-atelier` 皮肤工程改造：**代码骨架沿用原工程（CC BY-NC-SA 4.0），全部美术素材替换为 AI 生成的蜡笔小新主题素材**。

## 安装

```sh
# 1. 获取皮肤包（本仓库的 maid-atelier 目录）
git clone https://github.com/tinnyxx/dsh-xiaoxinxin-skin

# 2. 安装到 DSH web profile（pnpm 需要可用）
cd <harness>
dsh plugin --profile web add <克隆路径>/maid-atelier

# 3. 重启 DSH web，浏览器 Ctrl+F5 硬刷新
```

> 皮肤是纯展示层插件：卸载即完全还原，不注入服务、不触达模型请求。

## 功能

- 亮/暗双主题背景（春日部白天 / 夜晚），右下角 🌙/☀️ 开关随时切换（记忆选择）
- 左风间、右小新全高立绘，随页面相位移动/缩放
- Q 版小新侧栏吉祥物、四角装饰、底部红金波浪饰条
- 输入框四角装饰（复用侧栏四角素材）
- 新会话横幅、工作区缎带/盾徽、蝴蝶结设置按钮
- 卸载即复原（Cordis effect disposer 管理全部 DOM/CSS 写入）

## 素材与许可

- 皮肤代码与工程结构：**CC BY-NC-SA 4.0**（禁止商用，见 `LICENSE`）
- 美术素材：AI 生成的蜡笔小新主题二次创作（非商用）
- **蜡笔小新 IP 版权归臼井仪人 / 双叶社 / 相关版权方所有**。本皮肤仅供学习与个人使用，请勿商用、请勿用于任何商业场景
- 素材署名链详见 `maid-atelier/NOTICE`

## 目录结构

```
dsh-xiaoxin-skin/
├── README.md            # 本文件
└── maid-atelier/        # 皮肤包（dsh plugin add 的目标目录）
    ├── skin.json        # 皮肤中心元数据
    ├── cordis.patch.yml # bundle 补丁
    ├── lib/             # 预构建产物（运行时加载）
    ├── src/             # 源码
    ├── assets/          # 原始素材
    └── build/           # 构建预设
```

## 换图

把新图按槽位名放进目录后，重新烧录 base64 并重启 DSH web（见 `maid-atelier/README.md` 说明）。
