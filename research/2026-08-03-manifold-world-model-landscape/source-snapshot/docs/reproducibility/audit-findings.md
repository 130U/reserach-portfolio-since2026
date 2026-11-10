# 验证范围

## 研究证据

- 141 个来源、141 张来源卡和 111 条原子主张构成证据底座。
- 63 条页面证据映射覆盖 10 页演示稿。
- 五份研究档案对应 World Labs、Odyssey、Runway、Decart 和 NVIDIA Cosmos 3。
- 决策记录和 Content Lock 记录公开结论的批准依据。

## 当前交付

当前演示稿为 `manifold_world_model_landscape_v1_4.pptx`。其字节数和 SHA256 在交付清单中登记；同版本 PowerPoint 实机渲染记录覆盖 10 页，记录的文本框违规数为 0。

`scripts/audit/verify_repository.ps1` 核对文件清单、证据数量和交付哈希；`check_reader_text.ps1` 检查文本编码、不可移植引用、凭据特征及本机路径。`provenance/file_manifest.csv` 记录当前文件身份。

## 复现边界

来源卡记录研究日的证据内容和限制；并非每个原始网页都有不可变 HTML 或 PDF 快照。Agent 记录可追踪任务级分工，尚不包含逐条 Claim 的发现者映射。演示稿生成依赖 Codex 演示文稿运行时和指定字体，PowerPoint 实机渲染需要相应软件环境。

这些检查验证已发布材料的内部一致性，不更新 2026 年 7 月 14 日之后的产品或商业事实。具体命令见[复现指南](reproduction-guide.md)。
