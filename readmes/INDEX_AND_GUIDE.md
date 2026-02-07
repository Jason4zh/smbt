# Stickman Battle 游戏代码位置索引 - 使用指南

> 本文档集合包含了关于 Stickman Battle 游戏所有交互逻辑的完整代码位置映射。

---

## 📚 文档导航

### 包含的文档

本项目包含了以下几份详细文档:

#### 1. **GAME_INTERACTION_MAP.md** (主要) 🎯
   - 📖 页数: ~800行
   - 📍 内容: 完整的游戏交互逻辑映射
   - 💡 适合: 快速了解游戏全貌
   - 🎓 包括:
     - 游戏架构和入口流程
     - 武器系统详解 (100+种)
     - 角色系统 (玩家、敌人、AI)
     - UI系统完整列表
     - 游戏场景/关卡系统
     - 特效和音效系统
     - 数据系统和排行榜
     - 三个核心流程图

#### 2. **DETAILED_INTERACTION_GUIDE.md** (深度) 🔍
   - 📖 页数: ~600行
   - 📍 内容: 具体交互场景的深度分析
   - 💡 适合: 理解实现细节和控制流
   - 🎓 包括:
     - 场景A: 购买武器的完整流程
     - 场景B: 皮肤和颜色自定义
     - 场景C: 战斗中的武器使用
     - 场景D: 战斗结束和排行榜
     - 物理和碰撞系统
     - UI树形结构
     - 数据流向图
     - 本地数据结构
     - 扩展和定制指南

#### 3. **QUICK_REFERENCE.md** (速查) ⚡
   - 📖 页数: ~500行
   - 📍 内容: 路径速查表和完整文件清单
   - 💡 适合: 快速找到文件位置
   - 🎓 包括:
     - "你想找..."快速查找表
     - Assets目录完整树形结构
     - 所有文件的详细描述
     - 功能别快速查找
     - 关键数据格式
     - 调试提示

---

## 🎯 根据你的需求选择文档

### 我想知道...

#### 📌 "游戏是如何工作的？"
👉 **阅读**: [GAME_INTERACTION_MAP.md](./GAME_INTERACTION_MAP.md)
- 先读 "📋 目录结构概览"
- 然后读 "🎮 核心游戏交互逻辑"
- 最后看 "🔄 主要交互流程图"

#### 📌 "购买武器的代码在哪里？"
👉 **阅读**: [DETAILED_INTERACTION_GUIDE.md](./DETAILED_INTERACTION_GUIDE.md)
- 跳转到 "场景 A: 购买武器"
- 查看"用户操作路径"和"依赖的资源文件"

#### 📌 "怎样修改某个文件？"
👉 **阅读**: [QUICK_REFERENCE.md](./QUICK_REFERENCE.md)
- 查看"完整文件路径参考"
- 或使用"按功能快速查找"表格

#### 📌 "所有武器在哪里定义的？"
👉 **快速答案**:
1. 配置: `assets/prefabs/config.13be2.json`
2. 脚本: `assets/prefabs/index.13be2.js`
3. 预制件: `assets/prefabs/weapons/` (文件夹)
4. 图标: `assets/UI/weaponsIcons/`

#### 📌 "如何添加新关卡？"
👉 **读**: [DETAILED_INTERACTION_GUIDE.md](./DETAILED_INTERACTION_GUIDE.md)
- 搜索 "如何添加新关卡"

#### 📌 "排行榜数据存在哪里？"
👉 **快速答案**:
- 数据文件: `assets/resources/import/08/08c99f998.1b048.json`
- 配置: `assets/resources/config.cb4fa.json`
- 包含: 500玩家排行 + 8种语言翻译

#### 📌 "音效和特效系统怎样工作？"
👉 **读**: [GAME_INTERACTION_MAP.md](./GAME_INTERACTION_MAP.md)
- 查看 "8. 特效和音效系统"

---

## 🗺️ 详细内容导航

### 主要内容索引

| 主题 | 文档 | 位置 |
|------|------|------|
| 项目结构 | GAME_INTERACTION_MAP | 📋 目录结构概览 |
| 武器系统 | GAME_INTERACTION_MAP | 🔪 武器系统交互 |
| 角色系统 | GAME_INTERACTION_MAP | 👥 角色系统 |
| 皮肤系统 | GAME_INTERACTION_MAP | 🎨 皮肤系统 |
| UI系统 | GAME_INTERACTION_MAP | 🖥️ UI系统 |
| 场景系统 | GAME_INTERACTION_MAP | 🗺️ 游戏关卡系统 |
| 物品系统 | GAME_INTERACTION_MAP | 💎 游戏物品系统 |
| 音效特效 | GAME_INTERACTION_MAP | 🔊  特效和音效系统 |
| 数据系统 | GAME_INTERACTION_MAP | 📊 游戏数据系统 |
| 购买武器 | DETAILED_INTERACTION_GUIDE | 场景 A |
| 皮肤自定义 | DETAILED_INTERACTION_GUIDE | 场景 B |
| 战斗过程 | DETAILED_INTERACTION_GUIDE | 场景 C |
| 结束排行榜 | DETAILED_INTERACTION_GUIDE | 场景 D |
| 物理系统 | DETAILED_INTERACTION_GUIDE | 物理和碰撞系统 |
| UI树形 | DETAILED_INTERACTION_GUIDE | UI树形结构 |
| 数据流 | DETAILED_INTERACTION_GUIDE | 数据流向 |
| 扩展指南 | DETAILED_INTERACTION_GUIDE | 扩展和定制 |
| 文件路径 | QUICK_REFERENCE | 完整文件路径参考 |
| 快速查找 | QUICK_REFERENCE | 按功能快速查找 |
| 数据格式 | QUICK_REFERENCE | 关键数据格式 |

---

## 💻 核心代码位置速查

### 游戏启动
```
1. index.html ...................... 页面入口
2. main.9df48.js .................. 主启动脚本
3. src/settings.21c9d.js .......... 核心配置 ⭐
4. assets/main/index.000b4.js ..... Load.fire场景
```

### 武器相关
```
配置: assets/prefabs/config.13be2.json ⭐
脚本: assets/prefabs/index.13be2.js
UI: assets/prefabs/views/WeaponsView[2]
资源: assets/prefabs/weapons/
图标: assets/UI/weaponsIcons/
```

### 战斗场景
```
配置: assets/mainScenes/config.b305e.json ⭐
脚本: assets/mainScenes/index.b305e.js
数据: assets/mainScenes/import/03/0327f0caf.d403c.json
关卡: S1.fire ~ S39.fire (40多个场景)
```

### UI系统
```
配置: assets/UI/config.f3e2e.json ⭐
脚本: assets/UI/index.f3e2e.js
资源: assets/UI/ (所有UI元素)
视图: assets/prefabs/views/ (所有UI预制件)
```

### 音效系统
```
配置: assets/res/config.aa0dd.json ⭐
脚本: assets/res/index.aa0dd.js
文件: assets/res/audios/
```

### 特效系统
```
配置: assets/efffect/config.e3cbe.json ⭐
脚本: assets/efffect/index.e3cbe.js
资源: 各个plist文件
```

### 数据系统
```
配置: assets/resources/config.cb4fa.json ⭐
数据: assets/resources/import/08/08c99f998.1b048.json ⭐
包含: 排行榜 + 本地化
```

---

## 🎓 学习路径

### 初级: 理解游戏基础
1. 读 GAME_INTERACTION_MAP  
   - 📋 目录结构概览
   - 🎮 核心游戏交互逻辑 (前4项)
   - 🔄 主要交互流程图 (流程1)

**耗时**: ~30分钟

### 中级: 理解具体交互
1. 读 DETAILED_INTERACTION_GUIDE
   - 场景 A, B, C, D
   
2. 参考 QUICK_REFERENCE
   - 快速查找表

**耗时**: ~1小时

### 高级: 了解全部细节
1. 完整阅读所有文档
2. 查看每个关键点的具体文件
3. 理解数据流向和脚本架构

**耗时**: ~2-3小时

---

## 🔍 按功能快速定位

### Q: 如何修改特定内容？

#### 修改武器伤害
1. 找到: `assets/prefabs/config.13be2.json`
2. 修改: 对应武器的伤害值参数
3. 脚本: `assets/prefabs/index.13be2.js`
4. 效果: 下次战斗生效

#### 修改敌人难度
1. 找到: `assets/mainScenes/S*.fire` (目标关卡)
2. 编辑: 敌人AI类型和参数
3. 文件: `assets/prefabs/human/AI[1-3]`
4. 参数: HP, 攻击频率, 移动速度等

#### 修改界面文本
1. 找到: `assets/resources/locs`
2. 编辑: 对应语言的翻译
3. 文件: `assets/resources/import/08/08c99f998.1b048.json`

#### 添加新音效
1. 放置文件: `assets/res/audios/`
2. 注册: `assets/res/config.aa0dd.json`
3. 引用: 在对应脚本中调用

#### 修改UI按钮
1. 找到: `assets/prefabs/views/[ViewName]`
2. 编辑: 按钮位置和样式
3. 事件: 关联的脚本

---

## 📋 重要概念

### Bundle 系统
游戏分为9个独立的资源包:
- **internal** - 引擎内部
- **main** - 启动和加载
- **mainScenes** - 所有战斗场景
- **UI** - 界面资源
- **prefabs** - 预制件对象
- **Map** - 地图资源
- **res** - 音频资源
- **resources** - 数据文件
- **efffect** - 粒子效果

### 碰撞组 (22个)
详见 `src/settings.21c9d.js` 中的 groupList

### 物理引擎
- 基于 Cocos2d 内置
- 2D 刚体物理
- 碰撞矩阵控制交互

### 预制件系统
- 超过400个预制件
- 包括: 武器、环境、UI、效果
- 配置文件: `config.13be2.json`

---

## 🚀 快速开发参考

### 最常用的3个文件
1. `assets/prefabs/config.13be2.json` - 所有物品
2. `assets/mainScenes/config.b305e.json` - 所有场景
3. `src/settings.21c9d.js` - 游戏配置

### 最常修改的地方
1. 武器参数 → `prefabs/config`
2. 敌人难度 → `mainScenes/S*.fire`
3. UI文本 → `resources/locs`
4. 音效路径 → `res/config`

### 调试技巧
1. 检查浏览器控制台 (F12)
2. 在 `settings.21c9d.js` 启用调试
3. 使用浏览器DevTools查看文件大小
4. 检查Network标签查看加载

---

## 💾 文件大小参考

| 文件 | 大小 |
|------|------|
| cocos2d-js-min.9eb31.js | ~1.5 MB |
| mainScenes (bundle) | ~2-3 MB |
| UI (bundle) | ~1-2 MB |
| prefabs (bundle) | ~3-4 MB |
| 总体 | ~10-15 MB |

---

## 📞 常见问题解答

**Q: 游戏的源代码在哪里？**  
A: 这是一个编译后的Cocos Creator项目。原始.fire文件已打包为JSON，脚本已打包为.js。所有逻辑都在这些打包文件中。

**Q: 如何修改已发布的游戏？**  
A: 修改对应的配置文件（.json）或资源文件，然后重建项目。

**Q: 支持多少种武器？**  
A: 超过100种武器，具体数量见 `prefabs/config.13be2.json` 中的 paths 字段。

**Q: 有多少个游戏关卡？**  
A: S1.fire 到 S39.fire，共40个战斗场景，加上菜单场景。

**Q: 支持哪些语言？**  
A: 8种语言: 英、俄、德、西、法、意、葡、土

**Q: 排行榜数据多少？**  
A: 500名玩家，存储在 `resources/leaders`

---

## 📖 相关资源

### Cocos Creator 官方
- [官方文档](https://cocos.com)
- [API参考](https://docs.cocos.com/cocos2d-x)

### 本游戏特定
- 物理系统: 详见 `settings.21c9d.js` 碰撞矩阵
- UI系统: 详见各 `views/*` 预制件
- 音频系统: 详见 `res/config` 和 `index.aa0dd.js`

---

## 🎯 总结

这三份文档共同构成了 Stickman Battle 游戏的完整代码位置映射:

1. **GAME_INTERACTION_MAP.md** - 全局概览和架构
2. **DETAILED_INTERACTION_GUIDE.md** - 深度流程和实现
3. **QUICK_REFERENCE.md** - 速查表和文件清单

通过这些文档，你可以:
- ✅ 快速找到任何游戏功能的代码位置
- ✅ 理解游戏的完整工作流程
- ✅ 进行针对性的修改和扩展
- ✅ 调试和优化相关功能

---

**文档集合版本**: 1.0  
**创建日期**: 2026-02-07  
**语言**: 中文  
**编码**: UTF-8

---

## 📝 更新日志

### v1.0 (2026-02-07)
- ✅ 创建完整文档集
- ✅ 包含3份详细文档
- ✅ 覆盖所有游戏交互
- ✅ 提供快速查找表

---

**使用建议**: 
1. 从"按需选择文档"开始
2. 根据需求深入阅读
3. 使用QUICK_REFERENCE快速查找
4. 标记常用的位置以便快速查阅
