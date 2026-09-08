# 校园鲜达品牌图片生成记录

生成方式：Codex 内置 image generation 工具。

## 横版 Logo

输入参考：用户提供的“校园鲜达——新鲜到校·美好每一天”图片。

提示词要点：保留购物车与叶片图形、准确保留“校园鲜达”和“新鲜到校 · 美好每一天”、移除白色背景、输出透明背景横版网页资源，不添加其他文字。

输出：`static/images/campus_fresh_logo.png`，并由同一图形裁切生成 `campus_fresh_mark.png`。

## 首页空状态插画

提示词要点：透明背景、绿色校园生鲜配送场景、购物袋、果蔬、包裹、校园建筑与定位标记；不含文字、Logo 或水印。

输出：`static/images/campus_fresh_empty.png`。

## 登录页配送插画

输入参考：原 `static/images/login_banner.png`。

提示词要点：只将车辆侧面的旧“天天生鲜”替换为“校园鲜达”，保留道路、山景、车辆、包裹、透明背景和原构图。

输出：`static/images/campus_fresh_login_banner.png`。
