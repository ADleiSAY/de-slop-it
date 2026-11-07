# de-slop-it.skill

按语言和文体优化 AI 写作与对话的措辞，减少模板化表达，保留作者声音、事实与表达意图。

## 包含的 skills

| Skill | 用途 |
| --- | --- |
| [de-slop-it](skills/de-slop-it/SKILL.md) | 写作与润色总入口，按语言和文体读取方法论与例子 |
| [de-slop-it-compare](skills/de-slop-it-compare/SKILL.md) | 明确调用后比较版本，提炼修改方法 |
| [de-slop-it-examples](skills/de-slop-it-examples/SKILL.md) | 增加、修改、删除和整理表达例子 |

中文、英文分别包含正式写作、文学写作和对话规则。初始中文报告语料包含用户提供的改写偏好；英文规则为初始适配，可继续按使用反馈调整。

## 安装

克隆仓库，或从 GitHub 下载 ZIP 并解压。将 `skills/` 中的三个文件夹一起复制到 Codex 的 skills 安装目录：默认是 `~/.codex/skills/`；如果自定义了 `CODEX_HOME`，则使用其下的 `skills/`。

安装后应保持三个 skill 文件夹同级，子 skill 通过相对路径引用主 skill 的规则和语料。已有同名 skill 时，请先合并自己的修改，再更新文件。

## 使用

```text
$de-slop-it 按中文报告文体润色以下内容：……
$de-slop-it 修改中文文学规则：保留人物有意说出的短句。
$de-slop-it-compare B 是我修改的版本，请比较 A、B 并总结方法论。
$de-slop-it-compare 将上述方法写回中文正式写作规则，不增加例子。
$de-slop-it-examples 将以下改写对加入中文报告例子库：……
```

显示名为 `de-slop-it.skill`，实际调用名为 `$de-slop-it`。

## 设计与维护

- 总入口索引各语言、文体的独立 Markdown 文件，仅按需加载。
- 方法论和例子库分别维护，例子用于理解表达偏好，不作机械替换。
- 普通润色不自动修改 skill 文件。明确要求记住或更新规则时，才写回安装目录。
- 对比学习仅显式启用，默认总结方法；增加例子需要特别说明。
- 维护时先读取磁盘最新内容，保留用户已有修改。

版本比较依据具体改动分析；用户未标注修改者时，文本特征只能支持推测，不能确认作者身份。

## 许可证

[MIT License](LICENSE)，Copyright © 2026 ADleiSAY。
