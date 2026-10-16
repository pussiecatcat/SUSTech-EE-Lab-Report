# 南科大电子系实验报告 Skill

面向南方科技大学电子与电气工程系课程实验与项目的个人 Codex 技能。支持中英文写作，可选模板，并根据材料完整度提供排版、撰写和全局三种工作模式。

这是个人辅助工具，并非院系官方发布。仓库内的 Word 模板来自用户提供的《电子系实验报告模版.docx》，是否使用由每份报告单独选择。

## 工作方式

收到材料后，先阅读指导书、数据、截图、代码或已有报告，再集中确认尚未明确的选项。同一份报告补充文件时沿用已确认选择。

| 选择 | 选项 |
|---|---|
| 模板 | 电子系官方模板 / 其他指定模板 / 不使用模板 |
| 正文语言 | 中文 / 英文 |
| 工作模式 | 排版 / 撰写 / 全局 |
| 交付格式 | 仅 PDF / PDF + Word / PDF + LaTeX / PDF + Typst / Other（自行输入） |

可编辑源文件是可选交付物。Other 可填写其他格式或组合；如果交互工具已提供自由输入入口，直接使用该入口。

### 三种模式

- **排版**：基于已有正文和图表，处理样式、公式、编号、交叉引用、分页和导出。发现技术疑点时单独指出。
- **撰写**：依据已有实验结果组织分析和正文，完成必要的简单核算、图表整理及基本排版。
- **全局**：按需完成材料梳理、数据处理、编程或仿真、计算、绘图、分析、撰写、排版和最终检查。可靠的已有结果可以复用。

全局模式通常附上实际用到的分析代码、参数、处理后的数据和图文件。这些实验结果附件与报告的可编辑源文件分别处理；用户明确不要附件时遵循其选择。

## 安装

本仓库根目录就是技能目录，包含 `SKILL.md`、`agents/`、`references/` 和 `assets/`。将整个仓库放入个人技能目录，文件夹名称保持为 `sustech-ee-lab-report`。

Windows PowerShell 示例：

```powershell
$skillRoot = if ($env:CODEX_HOME) { Join-Path $env:CODEX_HOME 'skills' } else { Join-Path $env:USERPROFILE '.codex\skills' }
git clone https://github.com/pussiecatcat/sustech-ee-lab-report.git (Join-Path $skillRoot 'sustech-ee-lab-report')
```

如果目标目录已有同名技能，先保留自己的修改，再决定如何更新。也可以下载仓库 ZIP，解压后将技能目录放入上述位置。

## 使用示例

在对话中调用 `$sustech-ee-lab-report` 并提供材料。例如：

> 使用 $sustech-ee-lab-report。这里是实验指导书和原始数据，请使用中文、全局模式，不使用模板，交付 PDF 和 Typst 源工程。

> 使用 $sustech-ee-lab-report，只排版这份已有报告，采用官方模板，保留英文正文，仅交付 PDF。

没有提前指定的入口选项，技能会在阅读材料后询问。

## 文件说明

| 文件 | 用途 |
|---|---|
| [SKILL.md](SKILL.md) | 入口选择、模式边界和基本规则 |
| [agents/openai.yaml](agents/openai.yaml) | 技能展示名称与默认调用提示 |
| [assets/official-template.docx](assets/official-template.docx) | 可选的官方 Word 模板原件 |
| [references/analysis-and-writing.md](references/analysis-and-writing.md) | 数据处理、计算、绘图和写作方法 |
| [references/layout-and-output.md](references/layout-and-output.md) | 交付选择与 Word、LaTeX、Typst 工作路径 |
| [references/official-template.md](references/official-template.md) | 模板已核对的结构及适配方式 |
| [references/reference-lessons.md](references/reference-lessons.md) | 从历史报告提炼的可借鉴方法及来源链接 |
| [references/final-check.md](references/final-check.md) | 内容、结果、实际页面和交付文件检查 |

## 工具与验证范围

技能提供工作指引和模板资源，不内置 Word、LaTeX、Typst 编译器。具体生成能力依赖运行环境中的文档处理工具、字体、依赖和权限。使用时检查对应工具，并实际编译或导出、查看最终页面。

技能结构、资源链接和官方模板副本完整性已检查。当前版本尚未完成三种输出路径的完整报告端到端试跑；模板的文本和 OOXML 结构已核对，但尚未完成原件的独立页面渲染。

## 参考资料

写作方法参考 [SUSTech EE Course Hero](https://github.com/SUSTech-EE-Course-Hero/SUSTech-EE-Course-Hero) 中链接的 Wendy-Ying 报告，具体来源见 [reference-lessons.md](references/reference-lessons.md)。只提炼任务与结果对应、参数比较、图文结合和具体调试记录等方法，不机械复制其结果、篇幅、个人经历或版式。
