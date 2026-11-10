# 仓库地图

## 主阅读层

`docs/` 是面向人阅读的研究仓库入口，包括 Storyline、方法、日志、Agent、结果、五份清楚命名的对象 Dossier 和复现指南。

`docs/dossiers/` 只包含五份对象阅读版：World Labs、Odyssey、Runway、Decart 和 NVIDIA Cosmos 3。普通读者不需要理解内部对象编号、Phase 3 协议或查询审计文件。

## 原始输入

`inputs/original/` 保存：

- 两份 v2.0 治理文件；
- DR-01；
- DR-02；
- DR-03。

这些文件同时保留在原工作区归档中，便于核对输入登记和 SHA256。三份 DR 的阅读副本已移除 GitHub 无法解析的 ChatGPT 内部 `turn…` 引用标记；未经清理的初始版本可通过 Git 初始提交 `67f525c` 和输入清单中的原始 SHA256 追溯。

## 原工作区归档

工作区按研究输入、对象资格、来源与主张、综合结论和最终演示稿组织。决策记录保存研究判断的证据依据，`10_deck/` 提供当前 v1.4 演示稿及其生成与验证所需材料。

```text
00_brief     章程、状态、决策日志
01_inputs    输入副本和用户红队记录
02_anchor    Manifold 锚点
03_universe  对象、资格、地域和组件
04_evidence  来源登记、来源卡和 Ledger
05_candidates Phase 2 与检查点 2
06_dossiers  只保留五份对象 Dossier
06_dossier_support Dossier 方法、查询审计和完成 QA
07_synthesis 横向比较、矩阵和工作簿
08_content   Content Lock、Evidence Map 和冻结包
09_red_team  独立 Red Team
10_deck      当前 Storyboard、PPTX、渲染和 QA
```

## 生成程序

`archive/generation/` 保存当前演示稿的生成代码：

- `build_deck_v1_4.original.mjs`；
- `package.json`；
- `source-notes.txt`。

生成器使用相对路径、环境变量和包名导入。若要重新运行，仍需安装锁定版本的依赖，并为 Deck 临时目录设置 `MANIFOLD_DECK_TMP`（可选）。

## Provenance

`provenance/` 保存 Agent、工具、会话统计和仓库文件哈希清单。

公开脱敏范围和历史 ZIP 处理见 [`公开发布审计`](public-release-audit.md)。
