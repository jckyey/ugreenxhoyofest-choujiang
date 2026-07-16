# UGREEN × HSR Lucky Draw — 网页版

绿联 × 崩坏：星穹铁道 主题摇奖程序，原 Python 桌面程序（`UGREEN_HSR_Lucky_Draw.exe`）的纯网页版本。

## 功能特性

- 🎡 **转盘抽奖**：Canvas 绘制，3 秒缓动旋转 + 粒子爆裂特效，完全复刻原版加权随机算法
- 🌍 **中英双语**：界面一键切换，自动检测浏览器语言
- 📱 **移动适配**：桌面三栏 / 平板双栏 / 手机单栏 + 底部标签切换
- 💾 **本地存储**：数据存 localStorage，每设备独立，无需后端
- 📦 **单文件部署**：所有 CSS/JS/背景图内嵌于 `index.html`，零依赖、无构建步骤
- 🛠 **管理功能**：库存编辑（快捷 ±1/±5）、JSON 导入导出、CSV 导出、统计面板、撤销、清空历史

## 部署到 GitHub Pages

1. 在 GitHub 创建新仓库（如 `ugreen-hsr-lucky-draw`）
2. 上传本目录下的 `index.html` 和 `.nojekyll` 到仓库根目录
3. 进入 **Settings → Pages**
4. Source 选择 **Deploy from a branch** → 选 `main` 分支 → `/ (root)`
5. 保存后访问 `https://<用户名>.github.io/ugreen-hsr-lucky-draw/`

> 提示：`.nojekyll` 文件用于禁用 Jekyll 处理，确保页面正常加载。

## 本地预览

直接双击打开 `index.html` 即可（所有资源已内嵌，无需服务器）。
如需更真实的测试，可在项目目录运行 `python -m http.server 8000` 后访问 `http://localhost:8000`。

## 使用说明

- 点击中央 **SPIN/抽取** 按钮开始抽奖（空格键亦可）
- 左侧/「库存」标签页查看奖品剩余，点击 **Edit Stock/编辑库存** 调整数量
- 右上角齿轮菜单：导入/导出数据、CSV 导出、统计、清空历史、全部重置
- 语言切换：右上角 🌐 按钮

## 数据迁移

各区域同事在各自浏览器中使用，数据互相独立。如需跨设备备份或迁移：
- 用齿轮菜单 **Export JSON** 导出当前状态
- 在目标设备用 **Import JSON** 导入

## 抽奖算法说明

基于各奖品剩余数量进行加权随机抽取，「未中奖」权重 = 剩余总数 × 0.38。转盘扇区大小与抽奖概率严格成正比。
