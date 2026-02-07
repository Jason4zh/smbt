# Stickman Battle 游戏交互逻辑映射

> 📌 **说明**：此文档提供了游戏所有主要交互逻辑的代码位置映射

---

## 📋 目录结构概览

```
项目根目录
├── assets/
│   ├── main/                  # 加载场景 (Load.fire)
│   ├── mainScenes/            # 所有游戏主场景
│   ├── UI/                    # UI界面资源
│   ├── prefabs/               # 所有游戏物品预制件
│   ├── Map/                   # 地图资源
│   ├── res/                   # 音频资源
│   ├── resources/             # 数据文件（排行榜、本地化）
│   └── efffect/               # 粒子效果资源
├── src/
│   ├── settings.21c9d.js     # 游戏设置及碰撞矩阵配置
│   ├── cocos2d-js-min.9eb31.js
│   └── main.9df48.js
└── index.html
```

---

## 🎮 核心游戏交互逻辑

### 1. **游戏入口和加载流程**

| 交互 | 代码位置 | 说明 |
|------|--------|------|
| **游戏初始化** | `index.html` | 页面加载，Cocos2d引擎初始化 |
| **引擎配置加载** | `src/settings.21c9d.js` | 加载碰撞矩阵、物理组、分辨率等 |
| **启动场景** | `assets/main/index.000b4.js`<br>导入: `assets/main/import/b9/b920a4e7-523b-4056-aabf-13c09bef438b.652d0.json` | Load.fire 场景<br>进度条显示 |
| **Bundle加载** | `main.9df48.js` | 加载所有资源bundles |

### 2. **武器系统交互** 🔪

#### 2.1 武器选择/购买

| 交互功能 | 配置位置 | 说明 |
|--------|--------|------|
| **武器库** | `assets/prefabs/config.13be2.json` | 定义所有100+种武器 |
| **武器预制件** | `assets/prefabs/` | 每个武器的3D模型和物理属性 |
| **武器icons** | `assets/UI/config.f3e2e.json`<br>路径: `NewUI2/cell_weapon` | 武器选择UI中的图标 |
| **UI cell_weapon** | `assets/UI/` | 武器选择界面的单元格 |
| **UI cell_weapon_lock** | `assets/UI/config.f3e2e.json`<br>路径76: `cell_weapon_lock` | 未解锁武器的锁定显示 |

#### 2.2 武器列表

**常规武器 (weapons/)**
- `paintBrush` / `paintBrush2` - 画笔
- `hammer` / `hammer2` - 锤子
- `sword` / `sword2` - 剑
- `AK` / `AK2` - 枪（AK）
- `sniper` / `sniper2` - 狙击枪
- `axe` / `axe2` - 斧头
- `spear` / `spear2` - 矛
- `shield` / `shield2` - 盾牌
- `katanna` / `katanna2` - 刀
- `flail` / `flail2` - 连枷
- `scepter` / `scepter2` - 权杖
- 等等...

**特殊武器**
- `potion` / `potion2` - 药水
- `bomb` / `bomb2` - 炸弹
- `iceCream` / `iceCream2` - 冰淇淋
- `magnet` / `magnet2` - 磁铁
- ... 更多

#### 2.3 武器效果/子弹系统

| 子弹类型 | 位置 | 描述 |
|--------|------|------|
| `bullet/noteGreen2` | prefabs | 绿色音符子弹 |
| `bullet/notePurple` | prefabs | 紫色音符子弹 |
| `bullet/GreenBall` | prefabs | 绿色球体 |
| `bullet/guitaRed` | prefabs | 红色吉他弹 |
| `bullet/bomb2` | prefabs | 炸弹二代 |
| `bullet/arrows` | prefabs | 箭矢 |
| `bullet/cannonBall` | prefabs | 炮弹 |
| `bullet/energyBall` | prefabs | 能量球 |
| `bullet/rebound` | prefabs | 反弹子弹 |

### 3. **角色系统** 👥

#### 3.1 玩家

| 元素 | 位置 | 说明 |
|------|------|------|
| **主角模型** | `assets/prefabs/player/StickMan1` | 主角火柴人 |
| **物理设置** | `src/settings.21c9d.js` | 碰撞组: player1, player2 |
| **生命值体系** | 场景数据 | 在各battle场景中设置 |

#### 3.2 敌人/AI

| 元素 | 位置 | 说明 |
|------|------|------|
| **敌人模型** | `assets/prefabs/player/enemy` | 基础敌人模型 |
| **AI控制1** | `assets/prefabs/human/AI` | 简单AI |
| **AI控制2** | `assets/prefabs/human/AI2` | 中等AI |
| **AI控制3** | `assets/prefabs/human/AI3` | 高级AI |

### 4. **皮肤系统** 🎨

| 交互 | 位置 | 说明 |
|------|------|------|
| **皮肤选择界面** | `assets/prefabs/views/SkinsView` | 包括SkinsView, SkinsView2 |
| **皮肤资源** | `assets/UI/newSkins/texture` | 皮肤纹理资源 |
| **颜色选择** | `assets/prefabs/views/ColorsView` | 自定义颜色 |
| **颜色资源** | `assets/prefabs/Item/colorsItem` | 颜色物品 |

### 5. **UI系统** 🖥️

#### 5.1 主要UI视图

| UI视图 | 位置 | 功能 |
|--------|------|------|
| **MainView** | `assets/prefabs/views/MainView` | 主菜单界面 |
| **WeaponsView** | `assets/prefabs/views/WeaponsView`<br>WeaponsView2<br>NewWeaponsView | 武器选择界面 |
| **SkinsView** | `assets/prefabs/views/SkinsView`<br>SkinsView2 | 皮肤选择界面 |
| **ColorsView** | `assets/prefabs/views/ColorsView`<br>ColorsView2 | 颜色选择界面 |
| **ArenaView** | `assets/prefabs/views/ArenaView` | 竞技场选择 |
| **FinishView** | `assets/prefabs/views/FinishView` | 战斗结束界面 |
| **LeaderboardView** | `assets/prefabs/views/LeaderboardView` | 排行榜界面 |

#### 5.2 UI控制元素

| 元素 | 位置 | 说明 |
|------|------|------|
| **摇杆** | `assets/prefabs/views/JoyStick`<br>`JoyStick2` | 屏幕控制摇杆 |
| **金钱显示** | `assets/UI/NewUI2/money` | 金币/货币显示 |
| **等级进度条** | `assets/UI/NewUI2/pb_level_*` | 多个等级进度条 |
| **按钮** | `assets/UI/NewUI2/btn_*` | 各种按钮（绿、蓝、紫、黄等） |
| **手指提示** | `assets/UI/NewUI2/hand` | 交互提示指针 |
| **战斗按钮** | `assets/prefabs/Item/AtkBuff` | 攻击buff按钮 |

#### 5.3 UI配置详细

**UI Bundle路径**  
配置文件: `assets/UI/config.f3e2e.json`

关键UI资源:
- Path 0: `newSkins/texture` - 皮肤纹理
- Path 1: `NewUI2/rank_icon` - 排名图标
- Path 4: `NewUI2/popup_settings` - 设置弹窗
- Path 5: `NewUI2/skins_icon` - 皮肤图标
- Path 7: `NewUI2/bg_weapon_name` - 武器名称背景
- Path 10: `NewUI2/money` - 金钱显示
- Path 37: `NewUI2/arena` - 竞技场
- Path 38: `NewUI2/bg_shop_angle10` - 商店背景
- Path 49: `NewUI2/cell_weapon` - 武器单元格
- Path 76: `NewUI2/cell_weapon_lock` - 武器锁定

### 6. **游戏关卡/场景系统** 🗺️

#### 6.1 场景列表

| 场景 | 文件 | 类型 |
|------|------|------|
| **主场景** | `db://assets/mainScenes/main.fire` | 菜单/大厅 |
| **战斗场景** | `S1.fire` ~ `S39.fire` | 各个关卡 |

**场景分组 (部分列表)**
- S1 - S10: 早期关卡
- S11 - S20: 中期关卡  
- S21 - S30: 后期关卡
- S31 - S39: 困难及特殊关卡

配置位置: `assets/mainScenes/config.b305e.json`  
具体场景数据: `assets/mainScenes/import/03/0327f0caf.d403c.json`

#### 6.2 地形/地图元素

| 地形元素 | 位置 | 说明 |
|--------|------|------|
| **平台** | `assets/prefabs/mapElements/platform` | 基础平台 |
| **移动平台** | `assets/prefabs/mapElements/MovingPlatform` | 会移动的平台 |
| **旋转平台** | `assets/prefabs/mapElements/RotatingPlatform` | 会旋转的平台 |
| **跳跃垫** | `assets/prefabs/mapElements/Jumper` | 弹簧垫 |
| **墙体** | `assets/prefabs/mapElements/Walls` | 墙体障碍 |
| **传送门** | `assets/prefabs/mapElements/Portal` | 场景转移门 |
| **炸弹** | `assets/prefabs/mapElements/BombMap` | 可破坏炸弹 |
| **UP增益** | `assets/prefabs/mapElements/UP` | 向上推力 |
| **炮塔** | `assets/prefabs/mapElements/turret` | 自动射击炮塔 |

#### 6.3 背景资源

| 背景 | 位置 |
|------|------|
| 紫色背景 | `assets/Map/backgrounds/bg_violet` |
| 冬季背景 | `assets/Map/backgrounds/bg_winter` |
| 森林背景 | `assets/Map/backgrounds/bg_forest` |
| 太空背景 | `assets/Map/backgrounds/bg_space` |

### 7. **游戏物品系统** 💎

#### 7.1 物品类型

| 物品 | 位置 | 功能 |
|------|------|------|
| **武器物品** | `assets/prefabs/Item/weaponsItem` | 武器掉落 |
| **皮肤物品** | `assets/prefabs/Item/skinItem` | 皮肤掉落 |
| **颜色物品** | `assets/prefabs/Item/colorsItem` | 颜色掉落 |
| **Buff物品** | `assets/prefabs/Item/BuffItems` | 各种增益道具 |
| **攻击Buff** | `assets/prefabs/Item/AtkBuff` | 攻击力增加 |
| **提示物品** | `assets/prefabs/Item/Tips` | 游戏提示 |

### 8. **特效和音效系统** 🔊

#### 8.1 粒子效果

**效果Bundle**: `assets/efffect/config.e3cbe.json`

| 效果名称 | 位置 | 说明 |
|---------|------|------|
| Fire小 | `assets/efffect/firesmall` | 小火焰效果 |
| 爆炸 | `assets/efffect/deadBooms` | 角色死亡爆炸 |
| 武器命中 | `assets/efffect/playerWeaponHit` | 武器击中效果 |
| 能量球爆炸 | `assets/efffect/atom` | 原子爆炸效果 |
| 剑ACE效果 | `assets/efffect/swordAce` | 剑气效果 |
| 技能爆炸 | `assets/efffect/bigSkill` | 大招技能爆炸 |
| 药水效果 | `assets/efffect/eatPotion` | 喝药水特效 |

#### 8.2 音频资源

**音频Bundle**: `assets/res/config.aa0dd.json`

| 音效 | 类型 |
|------|------|
| `finish` | 游戏完成音效 |
| `click` | 按钮点击音 |
| `jump` | 跳跃音效 |
| `item` | 物品获得音效 |
| `explosion` | 爆炸音效 |
| `sword2` | 剑击音效 |
| `guitar` | 吉他音效 |
| `scepter` | 权杖音效 |
| `battle` | 战斗BGM |
| `bgm` | 菜单BGM |

### 9. **游戏数据系统** 📊

#### 9.1 数据存储

配置: `assets/resources/config.cb4fa.json`

数据文件: `assets/resources/import/08/08c99f998.1b048.json`

**数据内容**:
- **leaders** - 排行榜数据（500玩家，ID/评分/昵称）
- **locs** - 本地化数据（8种语言支持）
  - 中文、俄语、德语、西班牙语、法语、意大利语、葡萄牙语、土耳其语
- **game strings** - 游戏内字符串

### 10. **多人模式** 👥

| 模式 | 功能 |
|------|------|
| **1 Player** | 单人模式 |
| **2 Players** | 双人本地模式 |

**相关UI**:
- Path 32: `2_player_icon` - 双人图标
- Path 64: `1_player_icon` - 单人图标

---

## 🔄 主要交互流程图

### 流程 1: 从启动到选择武器

```
启动游戏
    ↓
index.html (页面加载)
    ↓
src/settings.21c9d.js (加载配置)
    ↓
main.9df48.js (初始化引擎)
    ↓
加载 main bundle
    ↓
Load.fire 场景 (进度条)
    ↓
加载其他 bundles (mainScenes, UI, prefabs...)
    ↓
main.fire 场景 (菜单)
    ↓
MainView (主菜单)
    ↓
选择模式 (1P/2P)
    ↓
WeaponsView (武器选择)
    ↓
SkinsView (皮肤选择)
    ↓
ArenaView (竞技场选择)
    ↓
开始战斗
```

### 流程 2: 武器购买/解锁

```
进入 WeaponsView
    ↓
显示武器列表 (cell_weapon)
    ↓
检查是否已购买
    ├─ 已购买 → 可选择
    └─ 未购买 → 显示锁定 (cell_weapon_lock)
    ↓
点击购买
    ↓
检查金币
    ├─ 足够 → 扣费，解锁武器
    └─ 不足 → 显示金币不足提示
    ↓
保存到本地数据
    ↓
刷新武器列表
```

### 流程 3: 战斗中的弹药/效果

```
选择武器
    ↓
进入战斗场景 (S1-S39)
    ↓
使用武器 (按攻击按钮)
    ↓
生成子弹/效果
    ├─ 伤害计算
    ├─ 播放效果 (efffect bundle)
    ├─ 播放音效 (res bundle)
    └─ 更新物理碰撞
    ↓
敌人受伤
    ├─ 掉落物品 (Item/*)
    └─ 播放爆炸效果
    ↓
继续战斗或结束 (FinishView)
```

---

## 🎯 核心交互点总结

| # | 交互名称 | 主要代码位置 | 关键数据 |
|---|--------|------------|--------|
| 1 | **游戏启动** | index.html → main.9df48.js | settings.21c9d.js |
| 2 | **武器选择** | assets/prefabs/views/WeaponsView | prefabs/config.13be2.json |
| 3 | **皮肤选择** | assets/prefabs/views/SkinsView | UI/newSkins/texture |
| 4 | **颜色选择** | assets/prefabs/views/ColorsView | prefabs/Item/colorsItem |
| 5 | **战斗场景** | assets/mainScenes/S1-S39.fire | mainScenes/config.b305e.json |
| 6 | **敌人AI** | assets/prefabs/human/AI* | mainScenes scenes |
| 7 | **UI控制** | assets/prefabs/views/JoyStick | mainScenes scenes |
| 8 | **武器效果** | assets/prefabs/bullet/* | efffect/config.e3cbe.json |
| 9 | **音效播放** | res/config.aa0dd.json | 各场景脚本 |
| 10 | **排行榜** | resources/leaders data | assets/resources/import/08 |
| 11 | **本地化** | resources/locs data | 8种语言翻译 |
| 12 | **物品掉落** | assets/prefabs/Item/* | 战斗场景脚本 |

---

## 📁 重要文件快速索引

| 功能 | 文件路径 |
|------|--------|
| 游戏配置 | `src/settings.21c9d.js` |
| 武器定义 | `assets/prefabs/config.13be2.json` |
| 场景定义 | `assets/mainScenes/config.b305e.json` |
| UI资源 | `assets/UI/config.f3e2e.json` |
| UI实现 | `assets/UI/index.f3e2e.js` |
| 场景脚本 | `assets/mainScenes/index.b305e.js` |
| 预制件脚本 | `assets/prefabs/index.13be2.js` |
| 地图资源 | `assets/Map/config.91766.json` |
| 音效资源 | `assets/res/config.aa0dd.json` |
| 数据文件 | `assets/resources/config.cb4fa.json` |
| 页面入口 | `index.html` |

---

## 🔧 开发提示

1. **修改武器**: 编辑 `assets/prefabs/` 中对应的武器预制件
2. **添加关卡**: 在 `assets/mainScenes/` 中添加新的 `.fire` 场景
3. **修改UI**: 编辑 `assets/prefabs/views/` 中的视图预制件
4. **调整难度**: 修改 `assets/mainScenes/` 中各场景的enemy配置
5. **添加语言**: 在 `assets/resources/` 中的 locs 数据添加新语言
6. **音效管理**: 在 `assets/res/` 中添加/修改音效资源
7. **特效优化**: 调整 `assets/efffect/` 中的粒子效果参数

---

**文档生成日期**: 2026-02-07  
**游戏引擎**: Cocos2d-js  
**版本**: Web-Mobile
