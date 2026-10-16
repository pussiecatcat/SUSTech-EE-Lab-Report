# 从参考报告提炼的方法

以下经验来自 [SUSTech EE Course Hero](https://github.com/SUSTech-EE-Course-Hero/SUSTech-EE-Course-Hero) 索引所链接的 Wendy-Ying 仓库。仓库所有者不等于每篇文档的唯一作者；此处只提炼方法，不复制个人结果和经历，也不把样例作为技术权威或固定版式。

## 可以采用的做法

| 做法 | 参考位置 | 何时有用 |
|---|---|---|
| 任务逐项对应实现、结果和解释 | [数字系统设计](https://github.com/Wendy-Ying/Digital-System-Design-Lab)、[STM32](https://github.com/Wendy-Ying/STM32-Learning) | 多个小实验、题目或模块需要逐项作答时 |
| 围绕参数或方案比较展开分析 | [通信原理](https://github.com/Wendy-Ying/Communication-Principles-Lab)、[工程电磁场](https://github.com/Wendy-Ying/Engineering-Electromagnetics-Lab) | 已有调制度、信噪比、滤波器参数或离散精度等可比结果时 |
| 关键程序、流程与运行证据相互对应 | [微处理器与微系统](https://github.com/Wendy-Ying/Microprocessors-and-Microsystems-Lab) | 嵌入式实验需要解释控制流程、接口和实物效果时 |
| 不同图承担不同解释任务 | [语音合成与感知](https://github.com/Wendy-Ying/Speech-Synthesis-And-Perception-With-Envelope-Cue) | 同一信号需要时域、频域或时频信息才能解释时 |
| 测量条件、读数与参照标准放在一起 | [移动机器人导航与控制](https://github.com/Wendy-Ying/Mobile-Robot-Navigation-and-Control-Lab) | 测距、标定和误差分析时；结论只适用于对应工况 |
| 经验落实到实际问题和修改 | [电子陶埙](https://github.com/Wendy-Ying/Electronic-Ocarina) | 用户有焊接、编译、调试或参数调整记录时 |
| 正文讲关键实现，长代码独立保存 | [语音合成与感知](https://github.com/Wendy-Ying/Speech-Synthesis-And-Perception-With-Envelope-Cue) | 程序较多而分析需要保持连贯时 |

## 选择性取用

这些资料体现具体课程和完成条件下的经验，不需要机械继承其工具限制、长代码、篇幅、通用背景、章节或视觉风格。可用现有工具改善计算、制图、表达和核查，但是否增加分析由本次任务和数据决定。

样例中出现过文字与表格排序不一致、指标名称与计算公式不一致，以及填写提示未删除等问题。这些说明需要独立核查，不应据此固化某个器件或算法的性能结论，也无需把所有历史问题逐条展示给报告读者。

参考范围内有表格外框、单栏编号章节和双栏论文等多种版式。不存在必须遵循的统一“Wendy-Ying 风格”；也没有通用的最佳页数。不要在每次调用时重新检索所有仓库，只有需要特定细节且已有材料不足时再打开相应来源。
