---
name: de-slop-it
description: 按语言和文体优化写作、对话及已有文本的措辞，减少模板化表达和 AI 味；支持用户明确要求的规则维护、版本对比学习和语料库增补。
---

# de-slop-it.skill

改善表达的连贯性、具体程度、情感和作者声音。实际调用名为 `$de-slop-it`。以用户当前要求为准，保留原稿事实、立场、确定程度、必要条件和有意设计的节奏。

## 总入口

先判断任务、语言和文体，仅读取相关文件。正式文体包含报告、汇报、论文和分析；文学与对话分别处理，混合文本按段落选用。

| 语言与文体 | 方法论 | 例子库 |
| --- | --- | --- |
| 中文正式写作 | [zh/formal.md](references/zh/formal.md) | 汇报、报告另读 [zh/report-examples.md](references/zh/report-examples.md) |
| 中文文学写作 | [zh/literary.md](references/zh/literary.md) | 暂无已收录语料 |
| 中文对话 | [zh/dialogue.md](references/zh/dialogue.md) | 暂无已收录语料 |
| 英文正式写作 | [en/formal.md](references/en/formal.md) | 暂无已收录语料 |
| 英文文学写作 | [en/literary.md](references/en/literary.md) | 暂无已收录语料 |
| 英文对话 | [en/dialogue.md](references/en/dialogue.md) | 暂无已收录语料 |

英文规则是基于初始偏好的语言适配，尚无用户英文修改样本。其他语言沿用保真、连贯、具体和符合读者习惯的原则，不照搬中文成语或标点习惯；用户要求长期维护该语言时，再建立对应文件并更新本表。

## 写作与润色

理解这段话由谁说、说给谁、要表达什么，再调整句法和措辞。方法论决定取舍，例子帮助理解偏好；例子不构成逐字替换表、禁词表或通用事实依据。

合并无意义的碎句，理顺已有的因果、时间和承接关系。保留有功能的短句、对比和术语；不得为了文风补造事实、引文、经历或因果。文学创作按用户允许的虚构范围展开。

默认直接交付成稿。用户要求解释时，再简述关键修改。普通润色不自动写回 skill，也不自动开启版本对比学习。

## 维护与子 skill

- **修改规则文件**：用户要求记住、加入或调整某项写作偏好时，读 [维护说明](references/maintenance.md)，修改对应语言、文体的文件。
- **对比学习**：仅在用户明确要求比较版本、识别人为修改版本并提炼方法时，读取 [de-slop-it-compare](../de-slop-it-compare/SKILL.md)。默认只分析和总结；明确要求更新方法论时才写回，未经特别要求不增加语料。
- **增加、修改或删除例子**：读取 [de-slop-it-examples](../de-slop-it-examples/SKILL.md)。此子 skill 维护本目录中的例子库，不把每个例子提升为普遍规则。

## 使用示例

- `$de-slop-it 按中文报告文体润色下面这段话。`
- `$de-slop-it 修改中文文学规则：保留人物有意说出的短句。`
- `$de-slop-it-compare B 是我改过的版本；比较 A、B 并将方法写入中文正式文体规则，不增加例子。`
- `$de-slop-it-examples 将以下改写对加入中文汇报、报告例子库。`
