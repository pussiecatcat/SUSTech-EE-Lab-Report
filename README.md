# 南科大电子系实验报告 Skill

面向南方科技大学电子与电气工程系课程实验与项目的个人技能，Claude Code 与 Codex 均可用。支持中英文写作，可选模板，并根据材料完整度提供排版、撰写和全局三种工作模式。

这是个人辅助工具，并非院系官方发布。

## 来源、版权与使用范围

- **不是院系发布物。** 本仓库由个人维护，与南方科技大学电子与电气工程系没有隶属或背书关系，也不代表院系的最新要求。
- **官方模板是外部提供的原件。** `assets/official-template.docx` 是《电子系实验报告模版.docx》的原始字节副本，版权归原权利人所有，本仓库不对其主张任何权利。院系对各课程的模板要求可能随时更新，**使用前以课程当次下发的文件为准**；是否使用该模板由每份报告单独选择，不选就不动它。
- **参考报告只取方法。** [references/reference-lessons.md](references/reference-lessons.md) 只从公开的课程报告仓库提炼写作方法并给出出处链接，不复制其中的数据、结论、成绩、个人经历或版式。
- **许可证是 MIT，但官方模板除外。** 技能本身（`SKILL.md`、`README.md`、`references/`、`agents/openai.yaml`）按 [LICENSE](LICENSE) 里的 MIT 条款授权。**`assets/official-template.docx` 不在该授权范围内**——它是第三方文件的副本，版权仍归原权利人，此处只作为工作资源提供；要连同它一起再分发，需自行确认是否有权这样做。模板原件按原始字节保留，不要为了这个目的去改动它。

## 工作方式

收到材料后，先阅读指导书、数据、截图、代码或已有报告，再集中确认尚未明确的选项。同一份报告补充文件时沿用已确认选择。

| 选择 | 选项 |
|---|---|
| 模板 | 电子系官方模板 / 其他指定模板 / 不使用模板 |
| 课程或项目名称 | 显示在页眉的课程名或项目名；用官方模板时必问 |
| 正文语言 | 中文 / 英文 |
| 工作模式 | 排版 / 撰写 / 全局 |
| 交付格式 | 仅 PDF / PDF + Word / PDF + LaTeX / PDF + Typst / Other（自行输入） |

可编辑源文件是可选交付物。Other 可填写其他格式或组合；如果交互工具已提供自由输入入口，直接使用该入口。

页眉放课程名、标题只写实验或项目名，课程信息不在两处重复。

### 三种模式

- **排版**：基于已有正文和图表，处理样式、公式、编号、交叉引用、分页和导出。发现技术疑点时单独指出。
- **撰写**：依据已有实验结果组织分析和正文，完成必要的简单核算、图表整理及基本排版。
- **全局**：按需完成材料梳理、数据处理、编程或仿真、计算、绘图、分析、撰写、排版和最终检查。可靠的已有结果可以复用。

全局模式通常附上实际用到的分析代码、参数、处理后的数据和图文件。这些实验结果附件与报告的可编辑源文件分别处理；用户明确不要附件时遵循其选择。

## 安装

本仓库根目录就是技能目录，包含 `SKILL.md`、`agents/`、`references/` 和 `assets/`。将整个仓库放入个人技能目录，文件夹名称保持为 `sustech-ee-lab-report`。

**Claude Code**（技能目录 `~/.claude/skills`），调用语法为 `/sustech-ee-lab-report`：

```powershell
git clone https://github.com/pussiecatcat/sustech-ee-lab-report.git (Join-Path $env:USERPROFILE '.claude\skills\sustech-ee-lab-report')
```

**Codex**（技能目录 `~/.codex/skills`），调用语法为 `$sustech-ee-lab-report`：

```powershell
$skillRoot = if ($env:CODEX_HOME) { Join-Path $env:CODEX_HOME 'skills' } else { Join-Path $env:USERPROFILE '.codex\skills' }
git clone https://github.com/pussiecatcat/sustech-ee-lab-report.git (Join-Path $skillRoot 'sustech-ee-lab-report')
```

`agents/openai.yaml`（技能展示名称与默认调用提示）只被 Codex 读取；在 Claude Code 下该文件不起作用，保留无害。其余文件两个环境通用，`SKILL.md` 的 frontmatter 只使用 `name`、`description` 和 `allowed-tools`，三者在两边都有效。

如果目标目录已有同名技能，先保留自己的修改，再决定如何更新。也可以下载仓库 ZIP，解压后将技能目录放入上述位置。

## 使用示例

在 Claude Code 中调用 `/sustech-ee-lab-report`（Codex 中用 `$sustech-ee-lab-report`）并提供材料。例如：

> 使用 /sustech-ee-lab-report。这里是实验指导书和原始数据，请使用中文、全局模式，不使用模板，交付 PDF 和 Typst 源工程。

> 使用 /sustech-ee-lab-report，只排版这份已有报告，采用官方模板，保留英文正文，仅交付 PDF。

没有提前指定的入口选项，技能会在阅读材料后询问。

## 文件说明

| 文件 | 用途 |
|---|---|
| [SKILL.md](SKILL.md) | 入口选择、模式边界和基本规则 |
| [agents/openai.yaml](agents/openai.yaml) | 技能展示名称与默认调用提示（仅 Codex 读取） |
| [assets/official-template.docx](assets/official-template.docx) | 可选的官方 Word 模板原件 |
| [references/analysis-and-writing.md](references/analysis-and-writing.md) | 数据处理、计算、绘图和写作方法 |
| [references/layout-and-output.md](references/layout-and-output.md) | 交付选择与 Word、LaTeX、Typst 工作路径 |
| [references/official-template.md](references/official-template.md) | 模板结构、正文嵌在单元格里带来的排版行为、页眉与标题分工、适配方式 |
| [references/reference-lessons.md](references/reference-lessons.md) | 从历史报告提炼的可借鉴方法及来源链接 |
| [references/final-check.md](references/final-check.md) | 内容、结果、实际页面和交付文件检查 |

## 工具与验证范围

技能提供工作指引和模板资源，不内置 Word、LaTeX、Typst 编译器。具体生成能力依赖运行环境中的文档处理工具、字体、依赖和权限。使用时检查对应工具，并实际编译或导出、查看最终页面。

`SKILL.md` 声明 `allowed-tools` 为 `Read`、`Write`、`Edit`、`Glob`、`Grep`、`Bash`：读取材料与已有报告、写出报告源文件、以及实际编译导出都需要这些工具，其中 `Bash` 用于调用 Typst、LaTeX、Python/MATLAB 和文档转换工具。这是可预授权的工具清单，不改变本技能关于硬件访问、外部上传和破坏性操作不自动获得授权的约定。

技能结构、资源链接和官方模板副本完整性已检查。2026 年 10 月 16 日以 EE323 Lab 2（离散时间系统）的真实材料完成了一次端到端试跑：从指导书和原始数据出发，经 MATLAB 计算与绘图、撰写、官方模板排版，到用 Word 导出 PDF 并逐页检查，产出 13 页英文报告。这次试跑验证了「官方模板 → Word → PDF」这条路径，并把两条实测结论写回了技能本身：

- 官方模板把整篇正文放在一个跨列的合并单元格里，Word 在该结构中不遵守 `w:tblHeader` 与 `w:keepNext`，会带来表头不重复、标题留在页脚、表格从表头后断开等问题；成因、对策与「不要用硬分页修」的理由见 [references/official-template.md](references/official-template.md)。
- 图的可读性必须按印制尺寸核算，不能只看源图是否清晰：半栏插入 7 in 宽的源图，等效字号只有 3 pt 左右；核算公式与重画源图的取舍见 [references/analysis-and-writing.md](references/analysis-and-writing.md)。

2026 年 10 月 17 日做了第二轮试跑，分两部分。

**一、给上一轮的核心结论补上对照组。** 上一轮说「正文嵌在合并单元格里会让 Word 忽略 `w:tblHeader`」，但那只是观察，没有排除其他解释。这一轮做了对照复现：同样一张 45 行表格、同样在首行写入 `w:tblHeader`（已确认该属性确实存在于保存后的 XML 里，不是没写进去），放进官方模板的合并单元格时跨页后表头不重现，放在普通文档顶层时表头正常重现。两次唯一的差异就是嵌套与否，因此嵌套结构确实是原因，该结论成立。顺带确认模板的 `styles.xml` 里连 `Table Grid` 都没有，用 python-docx 直接按名字取表样式会报 `KeyError`。

**二、补齐两条输出路径。** 第一轮用内容完全相同的短篇（标题 + 中英混排 + 编号公式 + 插图 + 表格 + 结论），第二轮加了多文件工程、bib 文献库和一张跨页长表，版式一律按官方模板的几何设置（A4，上下 25.4 mm、左右 31.75 mm）。

- **Typst 通过。** 字体写成逐字形回退的列表即可（拉丁用 Times、汉字落到微软雅黑），导出时字型全部嵌入。`#bibliography(..., style: "ieee")` 不需要外部工具链就能生成 [1][2][3] 式引用；但该 CSL 样式会按文档语言本地化（输出「3 版」「卷 61, 期 6, 页 692--702」并用《》包期刊名），课程严格要求英文 IEEE 版式时要核对渲染结果。
- **LaTeX 通过，ctexart 有四个坑。** `10.5pt` 选项被静默忽略，五号必须写成 `zihao=5`（ctex 的 `zihao` 只认 `5`、`-4`、`false`，写 `-5` 直接报错）；中文没有可用斜体字形，`\emph{}` 静默退化为正体；同样内容 ctexart 比 Typst 多占一页。
- **多文件 + biber 通过。** `\input` 分节、图放子目录、`biblatex`/`biber` 都正常，引用解析为 [1][2][3] 并生成参考文献；`latexmk -xelatex main.tex` 一条命令跑完整序列，不要手工漏跑轮次，漏跑产生的 `undefined references` 是中间态而非错误。
- **浮动体会把图推进参考文献页。** 实测正文第 1 页写着「如图 1 所示」，图却漂到第 3 页并落在参考文献标题下面。缩图（13.8 cm → 8 cm）后题注回到引用处且页数不变；`float` 的 `[H]` 会多出一页并留半页空白，`placeins` 的 `\FloatBarrier` 无效。页数受限时不要指望浮动体参数，先减内容。
- **绘图中文会静默丢字。** matplotlib 默认字体没有汉字字形，中文标签变成空框且只报 warning。回退到 SimHei 时还要关掉 `unicode_minus`。见 [references/analysis-and-writing.md](references/analysis-and-writing.md)。
- **DOCX → PDF 的自动化前提。** 这台机器没有 LibreOffice，Word COM 是唯一可行的自动导出方式，已实测可用，不需要手工打开 Word。

各项细节见 [references/layout-and-output.md](references/layout-and-output.md)。

仍未验证的范围：还没有用它产出过一份完整长度的课程报告；引用只测了数字顺序制，中文国标（`gbt7714`）、参考文献去重和多文献类型混排未试跑；上一轮提到的 `w:keepNext` 被忽略、标题留在页脚、H1 把整行推到下一页这几条，本轮只复现了 `w:tblHeader` 这一条。

## 参考资料

写作方法参考 [SUSTech EE Course Hero](https://github.com/SUSTech-EE-Course-Hero/SUSTech-EE-Course-Hero) 中链接的 Wendy-Ying 报告，具体来源见 [reference-lessons.md](references/reference-lessons.md)。只提炼任务与结果对应、参数比较、图文结合和具体调试记录等方法，不机械复制其结果、篇幅、个人经历或版式。
