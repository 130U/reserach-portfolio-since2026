# 复现指南

## 1. 运行仓库机械审计

```powershell
powershell -ExecutionPolicy Bypass -File scripts/audit/verify_repository.ps1
```

该脚本检查：

- 原工作区文件数；
- 141 来源、141 来源卡、111 Claim；
- 63 条 Evidence Map；
- 10 页最终 PPTX；
- Content Lock 和 v1.4 PPTX SHA256；
- 关键输入和文档是否存在。

## 2. 重建文件清单

```powershell
powershell -ExecutionPolicy Bypass -File scripts/audit/build_manifest.ps1
```

输出 `provenance/file_manifest.csv`，包含相对路径、字节数、修改时间和 SHA256。

## 3. 验证 Phase 4 工作簿

进入原工作区归档：

```powershell
cd archive/manifold-world-model-landscape/07_synthesis
node verify_phase4_workbook.mjs
```

期望结果：5 个对象、17 条信号、CSV/XLSX 单元格差异 0、公式错误 0。

## 4. 验证 Slide Evidence Map

```powershell
cd archive/manifold-world-model-landscape/08_content
node verify_slide_evidence_map.mjs
```

期望结果：63 行、10 页、Page 2 十对象、未解析引用 0、CSV/XLSX 差异 0、公式错误 0。

## 5. 构建文档站

```powershell
python -m pip install -r requirements-docs.txt
mkdocs build --strict
```

## 6. PPT 复现边界

当前生成器为 `archive/generation/build_deck_v1_4.original.mjs`，使用相对输入输出路径和可选的 `MANIFOLD_DECK_TMP` 临时目录。它依赖 Codex 提供的 `@oai/artifact-tool`；该运行时需要由执行环境提供，仓库不包含其安装包。

生成环境需要 Noto Sans SC 和 Noto Serif SC。最终实机验证使用 Microsoft PowerPoint 16 COM；`10_deck/tools/qa_deck_powerpoint.ps1` 接受 `InputPptx` 和 `OutputDir` 参数，核对字体、OOXML 与文本边界。生成后仍需人工逐页检查。

发布文件为 PPTX；研究证据的机械审计不要求重新生成演示稿。
