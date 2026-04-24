# 梦幻西游 AI Skills 知识库

《梦幻西游》电脑版 AI Agent 知识库，适用于 [OpenCode](https://opencode.ai) / Claude 等 AI 编码助手的 Skill 系统。

## 这是什么

一套结构化的梦幻西游游戏知识库，让 AI 能够准确回答梦幻西游相关问题，包括装备评估、宝石价格计算、副本攻略、召唤兽培养等。

数据来源：《梦幻西游》电脑版官网 https://xyq.163.com/introduce/

## Skill 列表

| Skill | 内容 |
|-------|------|
| [mhxy-game-intro](./mhxy-game-intro/) | 游戏介绍 — 背景故事、世界观、游戏特色、新手入门、快捷键、点数分配 |
| [mhxy-system](./mhxy-system/) | 系统介绍 — 聊天社交、交易摆摊、帮派系统、婚姻系统、家园住房、法宝坐骑 |
| [mhxy-activity](./mhxy-activity/) | 活动玩法 — 科举大赛、英雄大会、长安保卫战、挖宝封妖、二十八星宿等 |
| [mhxy-task](./mhxy-task/) | 任务介绍 — 师门、押镖、捉鬼、官职、种族任务、帮派任务、剧情副本 |
| [mhxy-battle](./mhxy-battle/) | 战斗综合 — 战斗规则、PK系统、五行相克、阵法、修炼、飞升、决斗 |
| [mhxy-pet](./mhxy-pet/) | 召唤兽 — 宠物概述、资质技能成长、炼妖打书、进阶特性、修炼、饰品 |
| [mhxy-equipment](./mhxy-equipment/) | 道具装备 — 20种武器、5类防具、宝石、暗器、套装、符石、灵饰、变身卡等 |
| [mhxy-skills](./mhxy-skills/) | 技能相关 — 生活技能、装备特技、打造缝纫炼金、剧情技能、暗器合成 |
| [mhxy-gem-price](./mhxy-gem-price/) | 宝石价格 — 按服务器区维护基准价，AI 自动计算任意等级合成成本 |
| [mhxy-weapon-eval](./mhxy-weapon-eval/) | 武器评估 — 9项评估指标，支持截图OCR输入，输出结构化评估报告 |
| [mhxy-common-info](./mhxy-common-info/) | 常用信息 — 传送坐标、练级地点、金钱上限、NPC合集、节日奖励 |
| [mhxy-tools](./mhxy-tools/) | 辅助工具 — 梦幻精灵、将军令、密保锁、角色交易、暂离保护等 |
| [mhxy-return](./mhxy-return/) | 老玩家回流 — 回流奖励、特殊服务器、新手礼包 |
| [mhxy-knowledge](./mhxy-knowledge/) | 装备与宝石基础知识（原型 Skill） |

## 安装使用

将 skill 文件夹复制到以下任一位置，AI 即可自动发现并加载：

```bash
# OpenCode 全局
~/.config/opencode/skills/

# OpenCode 项目级
.opencode/skills/

# Claude 兼容
~/.claude/skills/
~/.agents/skills/
```

或者直接 clone 本仓库后做软链接：

```bash
git clone <本仓库地址> ~/xyq_skills
ln -s ~/xyq_skills/mhxy-* ~/.config/opencode/skills/
```

## 特色功能

### 宝石价格计算
`mhxy-gem-price` 采用变量化设计，每个服务器区只需维护一张 1 级基准价表，AI 根据公式自动计算 1-10 级宝石和 1-4 级符石的合成成本。新增服务器只需复制模板填价格。

### 武器价值评估
`mhxy-weapon-eval` 支持截图 OCR 输入，自动计算：
1. 综合伤害（命中/3 + 伤害）
2. 综合物伤（人族/魔族/仙族三种族）
3. 综合法伤（五维加权公式）
4. 单点伤害售价（性价比指标）
5. 宝石成本（联动宝石价格 Skill）
6. 开孔成本（最低/平均）
7. 修理失败次数
8. 特技展示
9. 属性加点明细

## 维护说明

- 宝石价格更新：编辑 `mhxy-gem-price/SKILL.md` 中对应区的 1 级基准价表
- 新增服务器：复制文件内的模板，填入价格数据
- 游戏版本更新后，对应模块可能需要同步更新

详细变更记录见 [CHANGELOG.md](./CHANGELOG.md)

## 许可证

见 [LICENSE](./LICENSE)
