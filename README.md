# 🎄 Christmas Tree v17.6

一棵纯手写的粒子圣诞树，单文件 HTML，无任何依赖、无构建步骤。打开 `index.html` 就能看。

## 在线预览

开启 GitHub Pages 后：`https://<你的用户名>.github.io/christmas-tree/`

## 交互

| 操作 | 效果 |
| --- | --- |
| 拖动 / 滑动 | 绕 Y 轴旋转，松手带惯性 |
| 上下拖动 | 轻微俯仰视角 |
| 双击画面（或按空格 / 回车） | 切换配色：经典 → 冰晶 → 粉金 |

## 实现要点

- **树体**：约 3400 个粒子按圆锥方程 `r = R·(1−t)^0.88` 分布，叠加 `sin` 裙边让层次像树枝，底部更密。
- **螺旋灯串**：300 颗暖白灯泡沿 `t·9.5` 圈螺旋缠绕，各自独立的呼吸节奏。
- **透视**：手工 3D 投影，`scale = CAM_D / (CAM_D + z)`，越靠前的粒子越亮越大。
- **星空与落雪**：屏幕空间粒子，`globalCompositeOperation = 'lighter'` 叠加出光晕。
- **性能**：单 canvas 2D，DPR 上限 2，无阴影的粒子用 `fillRect` 批量绘制。

## 部署到 GitHub Pages

1. GitHub 新建公开仓库 `christmas-tree`（不要勾选 README，避免冲突）。
2. 上传 `index.html`、`.nojekyll`、`README.md` 到默认分支。
3. Settings → Pages → Source 选 `Deploy from a branch`，分支 `main`、目录 `/ (root)`，Save。
4. 等 1 分钟左右访问 `https://<用户名>.github.io/christmas-tree/`。

## 许可

随便用。Merry Christmas 🎁
