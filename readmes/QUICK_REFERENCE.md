# Stickman Battle 快速参考 - 资源和路径清单

## 📌 快速查找表

### 🎯 你想找...

#### 武器相关
- **所有武器定义**: `assets/prefabs/config.13be2.json`
- **武器脚本**: `assets/prefabs/index.13be2.js`
- **武器预制件文件夹**: `assets/prefabs/weapons/`
- **武器图标**: `assets/UI/` → `weaponsIcons/*`
- **武器选择界面**: `assets/prefabs/views/WeaponsView[2]` 或 `NewWeaponsView`

#### UI和菜单
- **主菜单**: `assets/prefabs/views/MainView`
- **所有UI视图**: `assets/prefabs/views/`
- **UI资源包**: `assets/UI/config.f3e2e.json`
- **UI脚本**: `assets/UI/index.f3e2e.js`
- **按钮图标**: `assets/UI/NewUI2/`
- **皮肤纹理**: `assets/UI/newSkins/texture`

#### 场景和关卡
- **关卡配置**: `assets/mainScenes/config.b305e.json`
- **场景脚本**: `assets/mainScenes/index.b305e.js`
- **关卡数据**: `assets/mainScenes/import/03/0327f0caf.d403c.json`
- **所有关卡**: `S1.fire` 到 `S39.fire`

#### 音效
- **音效列表**: `assets/res/config.aa0dd.json`
- **音效脚本**: `assets/res/index.aa0dd.js`
- **BGM位置**: `assets/res/audios/`

#### 特效
- **特效列表**: `assets/efffect/config.e3cbe.json`
- **特效脚本**: `assets/efffect/index.e3cbe.js`

#### 数据
- **排行榜数据**: `assets/resources/leaders`
- **本地化数据**: `assets/resources/locs`
- **数据文件**: `assets/resources/import/08/08c99f998.1b048.json`

---

## 📂 完整文件路径参考

### 顶级配置

```
/
├── index.html ........................... 游戏页面入口
├── cocos2d-js-min.9eb31.js ............. Cocos引擎(最小化)
├── main.9df48.js ....................... 项目主脚本启动
└── src/
    ├── settings.21c9d.js ............... ⭐ 游戏核心配置
    │   包含: collisionMatrix, groupList等
    └── style-mobile.25fc5.css .......... 移动样式
```

### Assets目录完整结构

#### 1. main/ - 启动和加载
```
assets/main/
├── config.000b4.json
├── index.000b4.js
└── import/b9/
    └── b920a4e7-523b-4056-aabf-13c09bef438b.652d0.json
        └── contains: Load.fire 场景
```

#### 2. mainScenes/ - 所有战斗场景
```
assets/mainScenes/
├── config.b305e.json ................ ⭐ 场景映射表
├── index.b305e.js .................. 场景脚本
├── import/03/
│   └── 0327f0caf.d403c.json ........ ⭐ 完整场景数据
└── native/ ......................... 编译后的资源
    ├── 12/, 16/, 1d/, 1e/, 37/, 3e/, 58/, 7e/, bd/, c7/, e3/
    └── 包含plist和资源文件
```

**场景列表** (简要):
- `main.fire` - 菜单
- `S1.fire` ~ `S10.fire` - 早期关卡
- `S11.fire` ~ `S20.fire` - 中期关卡
- `S21.fire` ~ `S39.fire` - 后期和困难关卡

#### 3. UI/ - 用户界面
```
assets/UI/
├── config.f3e2e.json ............... ⭐ UI资源映射
├── index.f3e2e.js ................. UI脚本
├── import/06/
│   └── 063fe732c.5d9cc.json ....... UI数据
└── native/
    ├── 2b/ ........................ 编译资源文件
    └── ...

UI资源包含的关键路径:
- newSkins/texture (路径0)
- NewUI2/ (所有UI元素)
  - money, btn_green_L, btn_blue_L等
  - cell_weapon, cell_weapon_lock
  - skins_icon, rank_icon
  - bg_shop_angle10 (商店背景)
  - hand (鼠标提示)
- weaponsIcons/ (所有武器图标)
- AllTexture/ (各种UI纹理)
```

#### 4. prefabs/ - 预制件和游戏对象
```
assets/prefabs/
├── config.13be2.json ............... ⭐ 预制件完整列表
├── index.13be2.js ................. 预制件脚本
├── import/06/
│   └── 0686912d6.5a4f4.json ....... 预制件数据
├── weapons/ ....................... 100+种武器模型
│   ├── sword, sword2
│   ├── AK, AK2
│   ├── hammer, hammer2
│   ├── ... (所有武器)
│   └── 等等
├── weaponsIcons/ .................. 武器图标
├── bullet/ ........................ 所有子弹类型
│   ├── normal, normalBig
│   ├── arrows, arrows2
│   ├── bomb, bomb2
│   ├── cannonBall, cannonBall2
│   ├── guitaRed, guitaGreen
│   ├── energyBall
│   └── ... (40+种子弹)
├── player/
│   ├── StickMan1 ................. 主角
│   └── enemy ..................... 敌人
├── human/
│   ├── AI ........................ 简单AI
│   ├── AI2 ....................... 中等AI
│   └── AI3 ....................... 高级AI
├── views/ ........................ UI视图预制件
│   ├── MainView .................. 主菜单
│   ├── WeaponsView ............... 武器选择1P
│   ├── WeaponsView2 .............. 武器选择2P
│   ├── NewWeaponsView ............ 新武器选择
│   ├── SkinsView ................. 皮肤选择1P
│   ├── SkinsView2 ................ 皮肤选择2P
│   ├── ColorsView ................ 颜色选择
│   ├── ColorsView2 ............... 颜色选择2
│   ├── ArenaView ................. 竞技场选择
│   ├── JoyStick .................. 摇杆1P
│   ├── JoyStick2 ................. 摇杆2P
│   ├── FinishView ................ 战斗结束
│   ├── LeaderboardView ........... 排行榜
│   ├── NicknameView .............. 昵称输入
│   ├── AudioView ................. 音频设置
│   ├── RondIn, RondOut ........... 过渡动画
│   ├── Tutorial1Player ........... 单人教程
│   ├── Tutorial2Players .......... 双人教程
│   ├── leaderItem ................ 排行榜项
│   └── flyMoney .................. 掉金币效果
├── mapElements/ .................. 地图元素
│   ├── platform .................. 平台
│   ├── MovingPlatform ............ 移动平台
│   ├── RotatingPlatform .......... 旋转平台
│   ├── Walls ..................... 墙体
│   ├── Jumper .................... 跳跃垫
│   ├── Portal .................... 传送门
│   ├── BombMap ................... 炸弹盒
│   ├── BoomEffects ............... 爆炸特效
│   ├── turret .................... 炮塔
│   ├── turretBullet .............. 炮塔子弹
│   ├── UP ........................ 推力
│   └── Propulseur ................ 推进器
├── effect/ ........................ 特效
│   ├── swordAce, swordAce2 ....... 剑气特效
│   └── playerWeaponHit ........... 武器打击
├── Item/ ......................... 物品和Buff
│   ├── weaponsItem ............... 武器掉落
│   ├── skinItem .................. 皮肤掉落
│   ├── colorsItem ................ 颜色掉落
│   ├── BuffItems ................. Buff物品
│   ├── AtkBuff ................... 攻击Buff
│   └── Tips ...................... 提示物品
└── native/ ....................... 编译资源
    ├── 1c/, 1f/, 2a/, 2d/, 4e/, 6a/, 80/, 94/, 9e/, b2/, b9/, f7/.plist文件

**子弹分类**：
- 箭矢系: arrows, arrows2
- 球形弹: energyBall, cannonBall, Upball等
- 爆炸系: bomb, bomb2, shareBoom
- 冻结系: iceMontagne, snowFlake
- 魔法系: scepterBall, lampRed等
- 剑气系: saberBall
```

#### 5. Map/ - 地图资源
```
assets/Map/
├── config.91766.json .............. ⭐ 地图资源配置
├── index.91766.js ................ 地图脚本
├── backgrounds/ .................. 背景纹理
│   ├── bg_violet ................. 紫色背景
│   ├── bg_winter ................. 冬季背景
│   ├── bg_forest ................. 森林背景
│   └── bg_space .................. 太空背景
└── NewMaps/ ...................... 新地图元素
    ├── NewAsset7_2
    ├── platform_forest
    ├── platform_space
    ├── platform_winter
    ├── wall_violet
    ├── wall_forest
    ├── wall_winter
    ├── wall_space
    ├── corner_wall_space
    ├── Portail_1
    ├── Bomb
    └── ... (20+种地图元素)
```

#### 6. res/ - 音频资源
```
assets/res/
├── config.aa0dd.json .............. ⭐ 音频资源列表
├── index.aa0dd.js ................ 音频脚本
├── import/04/
│   └── 0407761d9.a4a86.json ...... 音频数据
└── audios/ ....................... 音频文件
    ├── finish.mp3 ................ 游戏完成
    ├── jump.mp3 .................. 跳跃声
    ├── item.mp3 .................. 物品获取
    ├── explosion.mp3 ............. 爆炸声
    ├── sword2.mp3 ................ 剑击声
    ├── guitar.mp3 ................ 吉他声
    ├── scepter.mp3 ............... 权杖声
    ├── inhit.mp3 ................. 打击声
    ├── harp.mp3 .................. 竖琴声
    ├── battle (BGM) .............. 战斗音乐
    └── MenuAudios/
        ├── click.mp3 ............. 点击音
        └── bgm.mp3 ............... 菜单音乐
```

#### 7. efffect/ - 粒子效果
```
assets/efffect/
├── config.e3cbe.json .............. ⭐ 特效配置
├── index.e3cbe.js ................ 特效脚本
└── import/
    └── 包含ParticleAsset文件:
        ├── firesmall ............. 小火焰
        ├── upballPic ............. 上升球效果
        ├── guitaRedRun ........... 吉他红色
        ├── guitaGreenRun ......... 吉他绿色
        ├── noteRedBooms .......... 音符红爆炸
        ├── notePurpleBoom ........ 音符紫爆炸
        ├── noteGreenBoom ......... 音符绿爆炸
        ├── scepterRedBoom ........ 权杖红爆炸
        ├── lampgreen ............. 绿灯光
        ├── gauntletGreen ......... 绿拳套
        ├── atom .................. 原子爆炸
        ├── eatPotion ............. 喝药水效果
        ├── bormEffect ............ 射出效果
        ├── deadBooms ............. 死亡爆炸
        ├── potionBoom ............ 药水爆炸
        ├── playerWeaponHit ....... 武器命中
        └── armcannonGreen ........ 绿炮手臂

**计14种主要粒子效果**
```

#### 8. resources/ - 游戏数据
```
assets/resources/
├── config.cb4fa.json .............. ⭐ 资源配置
├── index.cb4fa.js ................ 资源脚本
└── import/08/
    └── 08c99f998.1b048.json ....... ⭐⭐ 关键数据文件

文件内容:
{
    leaders: [
        {id: 1, rating: 4990, nick: "superKing"},
        {id: 2, rating: 4980, nick: "Player#645883965"},
        ...
        {id: 500, rating: 0, nick: "Player#30691987"}
    ],
    locs: {
        // 8种语言翻译表
        'en': {...},
        'ru': {...},
        'de': {...},
        'es': {...},
        'fr': {...},
        'it': {...},
        'pt': {...},
        'tr': {...}
    }
}
```

#### 9. internal/ - 引擎内部
```
assets/internal/
├── config.52d36.json
├── index.52d36.js
└── import/05/
    └── 05464a930.3c4b0.json

内容: Cocos引擎内置脚本和资源
```

---

## 🎯 按功能快速查找

### 购买武器流程涉及的文件
1. `assets/prefabs/views/WeaponsView[2]` - UI显示
2. `assets/prefabs/config.13be2.json` - 武器定义
3. `assets/UI/NewUI2/money` - 金币显示
4. `assets/UI/NewUI2/btn_green_L` - 购买按钮
5. `assets/UI/NewUI2/cell_weapon_lock` - 锁定状态
6. 浏览器 LocalStorage - 保存玩家数据

### 战斗流程涉及的文件
1. `assets/mainScenes/S*.fire` - 关卡场景
2. `assets/prefabs/player/StickMan1` - 玩家角色
3. `assets/prefabs/human/AI[1-3]` - 敌人AI
4. `assets/prefabs/weapons/*` - 选中的武器
5. `assets/prefabs/bullet/*` - 子弹/效果
6. `assets/efffect/*` - 粒子效果
7. `assets/res/audios/*` - 音效

### 战斗结束和排行榜
1. `assets/prefabs/views/FinishView` - 结束界面
2. `assets/prefabs/views/flyMoney` - 金币动画
3. `assets/prefabs/views/LeaderboardView` - 排行榜
4. `assets/resources/leaders` - 排行旺数据
5. 浏览器 LocalStorage/Cloud - 存储

### 皮肤和颜色自定义
1. `assets/prefabs/views/SkinsView[2]` - 皮肤选择
2. `assets/UI/newSkins/texture` - 皮肤纹理
3. `assets/prefabs/views/ColorsView[2]` - 颜色选择
4. `assets/UI/NewUI2/cell_color` - 颜色单元格
5. `assets/prefabs/Item/colorsItem` - 颜色物品

### 多语言支持
1. `assets/resources/locs` - 所有翻译
2. 支持: 英、俄、德、西、法、意、葡、土 (8种)

---

## 💾 关键数据格式

### 武器数据 (示例)
```json
{
    "name": "sword",
    "damage": 10,
    "cooldown": 0.3,
    "bulletType": "bullet/normal",
    "price": 100,
    "icon": "weaponsIcons/sword",
    "unlocked": true
}
```

### 玩家数据 (LocalStorage)
```json
{
    "playerCoins": 5000,
    "playerScore": 2500,
    "unlockedWeapons": ["sword", "hammer", "AK"],
    "selectedWeapon": "sword",
    "selectedSkin": "skin1",
    "selectedColor": "#FF0000"
}
```

---

## 🔗 文件关系图

```
index.html
    ↓
main.9df48.js
    ↓
src/settings.21c9d.js (配置)
    ↓
加载 bundle:
    ├─ internal
    ├─ main → Load.fire
    ├─ mainScenes → main.fire + S1-S39.fire
    ├─ UI → 所有视图
    ├─ prefabs → 预制件
    ├─ Map → 地图/背景
    ├─ res → 音效
    ├─ efffect → 特效
    └─ resources → 排行榜/本地化
```

---

## 📊 性能关键指标

| 指标 | 值 |
|-----|-----|
| 目标帧率 | 60 FPS |
| 屏幕方向 | 横屏 (Landscape) |
| 设计分辨率 | 自适应 (mobile) |
| 物理步长 | 标准 (1/60) |
| 碰撞组数 | 22个 |
| 武器数量 | 100+ |
| 场景数量 | 40+ |
| 支持语言 | 8种 |

---

## 📢 调试提示

### 启用调试信息
修改 `src/settings.21c9d.js`:
```javascript
debug: true  // 改为 false 的地方
```

### 常见路径的相对查找
- 武器 → `prefabs/weapons/`
- 音效 → `res/audios/` 或 `res/MenuAudios/`
- UI → `UI/NewUI2/` 或 `prefabs/views/`
- 关卡 → `mainScenes/S*.fire`

---

**版本**: Cocos Creator Build  
**最后更新**: 2026-02-07  
**编码**: UTF-8
