# 坦克世界 · 点亮模拟器 (WoT Spotting Simulator)

基于《坦克世界》官方点亮机制的纯前端可视化模拟器。

## 功能

- 实时计算点亮距离（官方公式）
- 支持目标状态（静止 / 移动 / 刚开火）
- 草丛环境隐蔽加成 + 开火惩罚（15m 内降至 30%）
- 伪装网与额外加成
- 交互式雷达可视化（点击画布或拖动滑块）
- 完整公式展示与机制说明

## 部署到 Cloudflare Pages

1. 将整个 `wot-spotting-sim` 文件夹上传，或连接到 Git 仓库
2. 构建设置：无需构建（Framework preset 选 None）
3. 输出目录留空或填 `/`
4. 部署完成后即可访问

也可直接用 `npx serve .` 本地预览。

## 公式

```
点亮距离 = 视野 - (视野 - 50) × 隐蔽系数
```

- 隐蔽系数 ≥ 1 → 强制 50m
- 计算结果 > 445m → 实际最大仍为 445m
- 视野 > 445m 仍然有用（可抵消高隐蔽）

参考：[Wargaming Wiki - Camo and Spotting](https://wiki.wargaming.net/en/Camo_and_Spotting)
