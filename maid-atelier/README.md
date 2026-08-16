# maid-atelier · 蜡笔小新主题皮肤

DeepSeek Harness Web GUI 的蜡笔小新主题皮肤（基于 dsh-deep-whale 的 maid-atelier 工程）。纯展示层客户端插件——`apply()` 设置 `data-dsh-maid-atelier` 作用域、按亮/暗主题切换背景、以独立透明层挂载角色、装饰侧栏与输入框，并为加载/思考/工具运行状态预留动画钩子。effect 销毁器还原全部 CSS/DOM 写入；不注入服务、不发出 Cordis 事件、不触达模型请求。

## 安装

```sh
dsh plugin --profile web add <本目录>
```

加载即生效、卸载即复原（wiring.id 为 `ui-skin-maid-atelier`）。

## 换图（重要：三层缓存）

皮肤运行时**不直接读图片文件**，图片以 base64 内嵌在 `lib/client.js`。换图三步：

1. **重新烧录**：把新图按槽位名放入素材目录后，运行替换脚本把图片编码进 `lib/client.js` 与 `src/client/*-art.generated.ts`
2. **重启 DSH web**：服务端按启动时的 rev 哈希缓存 bundle，不重启不生效
3. **浏览器 Ctrl+F5** 硬刷新

> ⚠️ 浏览器对 CSS 变量中的 base64 data URI 有体积上限（约 2MB 量级），超限会静默丢弃。**素材请使用 WebP 格式**（本仓库素材均已转 WebP，全部远低于上限）。

## 素材

- 角色立绘、背景、装饰均为 AI 生成的蜡笔小新主题二次创作，透明底 WebP
- **蜡笔小新 IP 版权归臼井仪人 / 双叶社 / 相关版权方所有**：仅供学习与个人使用，禁止商用
- 皮肤代码遵循 CC BY-NC-SA 4.0（见 `LICENSE`、`NOTICE`）

## 构建

```sh
pnpm install
pnpm build    # tsdown 产出 lib/
```

## 许可

CC BY-NC-SA 4.0。见 `LICENSE` 与 `NOTICE`。
