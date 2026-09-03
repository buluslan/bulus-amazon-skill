<div align="center">

<img src="assets/banner.png" alt="bulus-amazon-skill" width="100%">

# 🛒 Bulus Amazon Skill

**13 个提示词，从零到一跑通亚马逊运营全流程——每步产出分档结论和动作清单，不是数据罗列**

**想了解更多最新AI行业动态,AI+电商/广告的行业实践方法,人与AI如何协作共生的思考,请关注公众号:【新西楼.AI】**

![qrcode_for_gh_e3b954bd3859_258](https://github.com/user-attachments/assets/d8f068d9-c4f8-46c7-914c-fbcab5d52f2a)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-SKILL-blueviolet.svg)](https://docs.anthropic.com/en/docs/claude-code)
[![Version](https://img.shields.io/badge/version-0.1.0-black.svg)]()

**市场体检 · 趋势验证 · 机会挖掘 · 竞品分层 · 分层词库 · Listing 生成 · 图片规划 · 广告开牌 · 复盘诊断 · 竞品雷达**

**Created By Buluu@新西楼.AI**

</div>

## 项目简介

你说一句「从零到一跑全流程」（或点名单个场景，如「做个市场体检」），Skill 会按真实运营时间轴调度 13 条场景提示词（需接入一个亚马逊数据源 MCP：卖家精灵 / SIF / Sorftime 均可，数据源中立），上游产出自动喂下游——体检定核心词 → 趋势验证 → 挖细分 → 竞品分层 → 深拆 → 反查 → 建词库 → 生成 Listing → 图片规划 → 广告开牌 → 复盘诊断，每一步都基于分档信号、假设排除、病因诊断做判断，输出的是「进不进、对标谁、先投哪些词、什么时候停」这类可执行结论。

它是 Agent 原生指令集：Claude Code / Codex / Cursor / OpenCode 等主流 Agent 均可运行。放进 Claude Code 的 skills 路径即可（Codex / Cursor 用户：把 SKILL.md 当指令喂给你的 Agent）。

它解决这些问题：

- ❌ 按搜索量排序选品，挤进只有曝光、没有订单的红海
- ❌ 拆竞品只抄文案关键词，学得了表面，学不了人家的决策
- ❌ 词库一张大平表，写文案的拿一半、投广告的拿另一半，上下文全断
- ❌ 广告效果一差就无脑降价关词——病因没找对，药全白吃

## ✨ 13 个场景

| 阶段 | 场景 | 你拿到什么 |
|------|------|-----------|
| 看市场 | 1 类目市场体检 / 2 趋势验证 / 3 细分机会挖掘 | 开放/寡头/衰退的分档判断 + 值得做的细分方向 |
| 定打法 | 4 竞品地图 / 5 单 ASIN 深度拆解 / 6 流量词反查 | 垄断/腰部/尾巴三层格局 + 对手的决策逻辑 + 抢得动的词 |
| 做上架 | 7 分层词库 / 8 Listing 生成 / 9 图片物料规划 | 五张分工词表 + 75 字符合规 Listing（带埋词对照）+ 7 张主图规划（附 AI 作图提示词）|
| 跑运营 | 10 广告开牌 / 11 广告复盘诊断 / 12 评论复盘 / 13 竞品雷达 | 三层匹配开牌方案 + 病因诊断处方 + 卖点验证清单 + 竞品动作还原 |

每条提示词自带三样设计：业务判断逻辑（不止查数据，先排除假设再下结论）、分档输出（四档/三层/四分类，不是平铺数据）、来源标注（每项数据标来源和统计周期）。

## 🚀 快速开始

**第一步：接入一个数据源 MCP**（以卖家精灵为例）

在你的 Agent 客户端添加 MCP 服务：

```
地址：https://mcp.sellersprite.com/mcp
Header：secret-key = 你的 MCP Key（卖家精灵开放平台 → 我的密钥）
```

**第二步：安装 skill**

```bash
git clone https://github.com/buluslan/bulus-amazon-skill.git ~/.claude/skills/bulus-amazon-skill
```

（其他 Agent：把仓库里的 SKILL.md 喂给你的 Agent 即可）

**第三步：说一句话**

```
用 bulus-amazon-skill 对「家居收纳」这个大类目跑一遍选品前三步
```

或者点名单场景：「帮我验证一下 storage organizer 这个词的趋势」「拆一下这个竞品 B0XXXXXXX」「给我的新品建词库」。

## 🏠 交流社区

<div align="center">

🎯 **更多 AI 实战教程和专属福利尽在我们「MBG 跨境AI实战圈」,已有 50+ 跨境大卖、AI 专家热聊中**

—— 欢迎跨境电商从业者加入我们,一起探索 AI+商业的最佳实践和真实边界,跑通【跨境AI】的从 0 到 1,打败你的同事,干掉你的老板。

**社区介绍:[mp.weixin.qq.com/s/dOz4fLmRnaFR7sD_TQm00Q](https://mp.weixin.qq.com/s/dOz4fLmRnaFR7sD_TQm00Q)**

<img width="1125" height="618" alt="image" src="https://github.com/user-attachments/assets/20f47cd6-e33c-4f3e-9362-3846c11135fd" />

</div>

## 📁 结构

```
bulus-amazon-skill/
├── SKILL.md               # 路由入口：数据源中立规则 + 13 场景调度逻辑
└── prompts/               # 13 个场景提示词（可单独复制使用）
    ├── 01-类目市场体检.md     # 类目值不值得进：容量/垄断度/价格带/新品存活 → 分档结论
    ├── 02-趋势验证.md         # 核心词在涨在跌：季节性/流量迁移/短期脉冲逐项排除再下判断
    ├── 03-细分机会挖掘.md     # 挖"新品真能拿到订单"的细分：点击/订单被头部锁死的假机会单独标出
    ├── 04-竞品地图.md         # 战场三层分层：垄断层/腰部层/尾巴层 + 价格战地图
    ├── 05-单ASIN深度拆解.md   # 还原对手决策逻辑：文案布局/变体矩阵/价格动作/评论信号
    ├── 06-流量词反查.md       # 对手的命门词 vs 新品抢得动的词，自然/广告排名分开看
    ├── 07-分层词库.md         # 五张分工清单：标题位/五点位/后台位/广告位/否定位
    ├── 08-Listing生成.md      # 吃前序全部数据生成 75 字符合规 Listing，附埋词对照表
    ├── 09-图片物料规划.md     # 7 张主图分工规划，每张附可直接使用的 AI 作图提示词
    ├── 10-广告开牌.md         # 按投入性价比三层分层：匹配方式/建议竞价/预算占比/否定预案
    ├── 11-广告复盘诊断.md     # 先找病因再开药：扩词/否词/调价/"不是广告的问题"四张处方
    ├── 12-评论复盘.md         # 主打卖点哪些被买家验证、哪些自嗨；差评按归因分类预警
    └── 13-竞品雷达.md         # 竞品销量异动 + 发券动作还原 + ABA 新词窗口雷达
```

提示词里的【数据MCP】【类目】【ASIN】都是占位符——Agent 执行时自动解析为你环境里实际接入的数据源和你的输入。

## 📜 License

MIT License © 2026 [buluslan](https://github.com/buluslan)

## 📖 写在最后

<div align="center">

**如果这个工具帮到了你,欢迎 ⭐ Star 支持。更多 AI × 跨境电商实操内容,关注公众号「新西楼.AI」。**

</div>
