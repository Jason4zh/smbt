# StickmanBattle - 火柴人战斗游戏
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Deployed-brightgreen)](https://jason4zh.github.io/smbt/)  

一款无广告、无限资源的火柴人对战游戏，基于Cocos2d-JS开发，适配移动端/PC端，已部署至GitHub Pages，开箱即玩！

## ✨ 核心亮点
### 🚫 无广告纯净体验
移除游戏内所有广告（弹窗/插屏/激励广告），无等待、无强制广告打断，打开即畅玩，专注纯粹的游戏体验。

### 💰 无限资源畅玩到底
游戏初始化自动配置海量核心资源，无需肝任务/充值，直接解锁全部内容：
- 无限金币：初始 `1145141919810`，任意购买道具/解锁内容；
- 无限钥匙：初始 `31415926`，解锁宝箱/特殊玩法无限制；
- 全武器解锁：8大系列 × 40款武器（总计80款）全部开放；
- 全皮肤解锁：40款角色皮肤自由更换；
- 高阶初始等级：玩家等级直接拉满至 `9177`，跳过新手养成；
- 全教程解锁：默认跳过基础/商店/双人教程，直接体验核心对战。

### 📱 多端适配+全屏体验
- 支持PC/移动端浏览器访问，自动适配横竖屏（默认横屏）、多分辨率；
- 内置全屏模式按钮，点击即可沉浸式对战（10秒自动隐藏，点击屏幕边缘呼出）；
- 兼容Chrome/Firefox/Safari/微信/QQ浏览器等主流环境。

## 🎯 快速开始（GitHub Pages 访问）
直接点击下方链接即可游玩，无需本地部署：  
👉 [https://jason4zh.github.io/smbt/](https://jason4zh.github.io/smbt/)  

### 本地运行（可选）
若需本地调试，克隆仓库后直接打开 `index.html` 即可：
```bash
# 克隆仓库
git clone https://github.com/jason4zh/smbt.git

# 进入目录，用浏览器打开 index.html
cd smbt
open index.html  # 或双击文件打开
```

## 📁 项目结构
```
smbt/
├── index.html               # 游戏主入口（资源初始化+全屏配置）
├── style-mobile.25fc5.css   # 移动端样式
├── src/
│   └── settings.21c9d.js    # 游戏基础配置
├── main.9df48.js            # 游戏核心逻辑
├── cocos2d-js.js / cocos2d-js-min.9eb31.js  # Cocos2d引擎
└── physics.js / physics-min.js              # 物理引擎（可选）
```

## ⚙️ 关键配置说明
### 资源自定义（可选）
游戏初始资源在 `index.html` 的 `initGameData()` 函数中定义，可按需修改：
```javascript
// 示例：修改初始金币/钥匙
var gameData = {
  gold: 999999999999,  // 自定义金币数量
  keys: 99999999,       // 自定义钥匙数量
  level: 9999,          // 自定义初始等级
  // ... 其他配置
};
```

### 数据存储
游戏数据保存在浏览器 `localStorage`（key: `p27`），清除缓存会重置数据；如需重置资源，删除 `localStorage.p27` 后刷新页面即可自动重新初始化。

## 🖥️ 兼容说明
| 环境                | 要求                          |
|---------------------|-------------------------------|
| 浏览器              | Chrome 80+ / Firefox 75+ / Safari 13+ |
| 移动端              | iOS/Android 浏览器（关闭缩放）|
| 全屏支持            | 标准全屏API / X5内核 / 360浏览器 |

## 📝 注意事项
1. GitHub Pages 部署后，确保所有静态资源路径正确（相对路径已适配）；
2. 部分浏览器可能限制全屏功能，需手动允许「全屏权限」；
3. 禁用右键菜单以避免操作干扰，专注游戏体验；
4. 音量/音效默认保留50%，可在游戏内自行调整。

## 💻 部署到 GitHub Pages
若需自行部署，参考以下步骤：
1. 将项目推送到 GitHub 仓库；
2. 进入仓库 → Settings → Pages；
3. 选择 `main` 分支，根目录 `/`，点击 Save；
4. 等待几分钟，访问 `https://你的用户名.github.io/仓库名/` 即可。

## 🎮 体验优化
- 加载完成后自动隐藏进度条，无需手动关闭；
- 适配移动端触摸操作与PC端键鼠操作；
- 本地数据持久化，刷新页面不丢失进度（清除缓存除外）。

Enjoy the game! 🎉  

---
*注：替换上述链接中的 `jason4zh` 和 `仓库名` 为你的GitHub用户名和实际仓库名称。*