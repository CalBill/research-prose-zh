<div align="center">

<img src="docs/assets/banner.svg" alt="中文文档表达：让文字自然，让论述连贯" width="100%">

# 中文文档表达

**让 AI 把文档写得自然、清楚，保留值得读的内容。**

<p><a href="./SKILL.md"><img src="https://img.shields.io/badge/Agent_Skill-v0.2-234F50?style=flat-square" alt="Agent Skill v0.2"></a> <a href="#install"><img src="https://img.shields.io/badge/安装-Codex-234F50?style=flat-square" alt="安装到 Codex"></a> <a href="./references/examples.md"><img src="https://img.shields.io/badge/内容-规则与示例-B77948?style=flat-square" alt="规则与示例"></a> <a href="./LICENSE"><img src="https://img.shields.io/badge/License-MIT-64756C?style=flat-square" alt="MIT License"></a></p>

<p>适用于公司与行业研究、策略备忘录、技术分析及其他中文说明材料。<br>Word · WPS · 飞书 · Markdown · 聊天中起草的文档正文</p>

**[改写对比](#examples) · [安装使用](#install) · [与 Caveman 的区别](#comparison) · [写作规则](./SKILL.md)**

</div>

---

<table>
<tr>
<td width="33%" valign="top"><strong>自然的措辞</strong><br><br>说清对象、动作和关系，减少生硬的名词组合与含糊黑话。</td>
<td width="33%" valign="top"><strong>连贯的论述</strong><br><br>保留转折、因果与解释关系，让句子连续推进，段落充分展开。</td>
<td width="33%" valign="top"><strong>有分寸的编辑</strong><br><br>删去没有额外信息的提醒，保留事实、归因和影响判断的具体条件。</td>
</tr>
</table>

<a id="examples"></a>

## 先看改写对比

以下为编辑示例，展示规则如何影响措辞与论述。

### 01 · 删去重复提醒，让事实直接出现

<table>
<tr><th width="50%" align="left">原文</th><th width="50%" align="left">改写</th></tr>
<tr>
<td valign="top">管理层称公司市场份额行业第一，但这一说法仍需独立核验，不能直接作为已经确认的事实结论。</td>
<td valign="top">管理层称公司市场份额位居行业第一。</td>
</tr>
</table>

“管理层称”已经交代意见来源。在语言编辑任务中，无需再加一句泛泛的核验提醒。

### 02 · 把生硬的抽象表达写清楚

<table>
<tr><th width="50%" align="left">原文</th><th width="50%" align="left">改写</th></tr>
<tr>
<td valign="top">费马大定理形式化的价值在于把既有证明转成可检查的实现。</td>
<td valign="top">费马大定理的形式化工作，主要是将已有证明写成计算机可以检查的形式。</td>
</tr>
</table>

把“谁检查什么”交代出来，句子可以稍长一些。

### 03 · 保留转折，让解释接在判断后面

<table>
<tr><th width="50%" align="left">原文</th><th width="50%" align="left">改写</th></tr>
<tr>
<td valign="top">内部渠道销量超过一半。外部渠道收入超过一半。两个渠道的产品结构不同，这是解释上述差异的原因之一。</td>
<td valign="top">内部渠道销量超过一半，但收入主要来自外部渠道，产品结构差异是其中一个原因。</td>
</tr>
</table>

销量与收入的转折仍然清楚，产品结构仍用于解释两者的差别。

<details>
<summary><strong>有些文字，本来就应该保留</strong></summary>

> 公司预计，若新增门店六月前开业，且下半年单店收入达到去年平均水平，全年收入有望增长12%。预测未计入仍在选址的项目。

这段已经清楚。开业时点、单店收入假设、预测属性和未计入的项目都有具体含义，应当保留。

“对新进入者而言”“模型负责研究推理的工作”等自然搭配，也不必为了少几个字而压缩。

</details>

更多说明见 [改写示例](./references/examples.md)。

<a id="install"></a>

## 安装到 Codex

**安装文件**让 Codex 能读取这套规则，**配置全局指令**让未来各项目的文档任务默认采用。下面两种方式任选一种。

### 方式一：让 Codex 帮你安装

在本机 Codex 中新建一个任务，将下面整段发给它：

```text
请从 https://github.com/CalBill/research-prose-zh 安装“中文文档表达”Skill。

安装到我的用户级技能目录 ~/.agents/skills/research-prose-zh，
并在 ~/.codex/AGENTS.md 中追加规则：
以后在任何项目中起草、改写或润色中文文档正文时，先读取并遵循该 Skill，
覆盖 Word、WPS、飞书、Markdown 及聊天中交付的文档草稿。
日常聊天、纯格式转换和仅排版任务不默认采用。
用户明确指定其他文风时，按当次要求调整。

保留现有全局指令。如果安装目录已存在，先检查来源与本地修改，
备份后再更新，不直接覆盖。完成后核对文件和全局规则，告诉我安装路径。
```

这会安装到当前电脑。其他电脑需要分别安装。仓库公开，下载不需要 GitHub 账号。

<details>
<summary><strong>方式二：自己在终端安装</strong></summary>

### 第一步：下载 Skill

需要先安装 [Git](https://git-scm.com/downloads)。以下命令在 macOS、Linux 或 WSL 的**终端**执行：

```bash
mkdir -p "$HOME/.agents/skills"
git clone https://github.com/CalBill/research-prose-zh.git "$HOME/.agents/skills/research-prose-zh"
```

Windows PowerShell 使用：

```powershell
New-Item -ItemType Directory -Force "$HOME\.agents\skills" | Out-Null
git clone https://github.com/CalBill/research-prose-zh.git "$HOME\.agents\skills\research-prose-zh"
```

如果提示目标目录已存在，先检查已安装的版本与本地修改，不要直接删除。可改用上面的 Codex 安装提示，让它处理更新。

### 第二步：配置文档任务默认采用

在用户目录中找到 `.codex/AGENTS.md`，不存在时创建。用文本编辑器打开，将下面内容**追加到末尾**，保留已有指令：

```markdown
## 中文文档写作默认规则

- 起草、改写或润色中文文档正文时，先读取并遵循
  ~/.agents/skills/research-prose-zh/SKILL.md，按需要读取其中链接的示例。
- 适用于所有项目的 Word、WPS、飞书、Markdown 等文档，
  包括直接在聊天中交付的文档草稿，无需再次点名 Skill。
- 日常聊天、纯格式转换和仅排版任务不默认采用。
  用户明确指定其他文风时，按当次要求调整。
```

文件路径对应关系：

| 用途 | macOS / Linux / WSL | Windows |
| --- | --- | --- |
| Skill 主规则 | `~/.agents/skills/research-prose-zh/SKILL.md` | `%USERPROFILE%\.agents\skills\research-prose-zh\SKILL.md` |
| 全局指令 | `~/.codex/AGENTS.md` | `%USERPROFILE%\.codex\AGENTS.md` |

若设置了自定义 `CODEX_HOME`，全局指令应放在该目录下。若该目录已有非空的 `AGENTS.override.md`，Codex 会优先读取它，需要在实际生效的文件中加入规则。

加载机制见 [Codex 技能说明](https://learn.chatgpt.com/docs/build-skills)和[全局指令说明](https://learn.chatgpt.com/docs/agent-configuration/agents-md)。

</details>

### 安装后，怎样确认生效？

**新开一个 Codex 任务**，发给它：

```text
请改写这段文档正文：
费马大定理形式化的价值在于把既有证明转成可检查的实现。

改写后，请列出本次实际读取的写作规则文件路径和版本。
```

检查它是否实际读取了 `research-prose-zh/SKILL.md`，版本是否为 `0.2`。既要看文件读取记录，也要看修改后的文字是否更清楚。若技能未出现或全局规则未加载，重启 Codex 后重新开任务。

### 日常怎么用？

完成全局配置后，直接交代文档任务即可：

```text
帮我修改这份行业研究正文，保留观点和数据，理顺表达。
```

```text
根据这些材料起草一份策略备忘录，读者是投资与技术同事。
```

只想单次使用时，可以明确写：

```text
请使用 $research-prose-zh 润色下面的文档正文。
```

<details>
<summary><strong>后续更新与停用</strong></summary>

通过 `git clone` 安装，且安装目录没有自己的未提交修改时，在终端执行：

```bash
git -C "$HOME/.agents/skills/research-prose-zh" pull --ff-only
```

手动复制安装的目录不支持直接 `git pull`。可以将“方式一”的提示改成“更新现有安装”，让 Codex 核对来源、备份定制内容后同步。

停止默认使用时，删去全局指令中对应的“中文文档写作默认规则”段落，并重新开任务。若要卸载，再移除技能目录；只删除全局规则后，Skill 仍可能根据文档任务自动匹配或被明确调用。

</details>

<a id="comparison"></a>

## 与 Caveman 的区别

[Caveman](https://github.com/JuliusBrussee/caveman) 的 README 将目标、示例和安装入口放在显眼位置，本页参考了这种组织方式。两者处理的问题不同：

| 维度 | Caveman | 中文文档表达 |
| --- | --- | --- |
| 主要目标 | 减少 Agent 读入和输出的 token，并提供相关效率工具 | 改善中文文档的措辞、句法和段落组织 |
| 表达取向 | 强调简短直接，提供不同压缩程度的输出模式 | 按论述需要安排长短，保留自然搭配与解释关系 |
| 产品形式 | 当前 README 介绍了写作 Skill、CLI、输入压缩、模型路由等功能 | 指令与示例组成的 Skill，无额外运行依赖 |
| 默认应用范围 | 面向 Agent 交互及编程工作流 | 文档起草、改写与润色，日常聊天不默认采用 |
| 效果展示 | 项目提供 token 与成本测试及其方法说明 | 当前提供编辑示例和用户反馈，尚无跨模型量化结果 |

这里的比较依据 [Caveman README](https://github.com/JuliusBrussee/caveman/blob/main/README.md) 的项目介绍。上面的改写示例用于说明编辑取舍，后续会结合实际任务继续完善。

## 适用于其他 Agent 吗？

支持 `SKILL.md` 格式的 Agent，可按其技能目录要求安装整个文件夹。没有技能机制时，可在文档任务前要求它读取主规则和相关示例。

如需默认采用，将相同的文档调用要求加入目标 Agent 的长期指令。`agents/openai.yaml` 是 Codex 的显示配置，其他工具按自身格式处理。

## 文件与迭代

```text
research-prose-zh/
├── SKILL.md                  主规则、适用范围和编辑要求
├── agents/openai.yaml        Codex 显示名称与默认提示
├── references/
│   ├── examples.md           改写示例与编辑判断
│   └── calibration.md        样本校准和规则更新方法
├── docs/assets/banner.svg    README 横幅
└── LICENSE                   MIT 许可证
```

当前版本 **v0.2**，由范文观察、实际改稿和用户反馈整理而成。Skill 在任务中提供规则与示例，未训练或微调模型。文件生成、排版和平台操作由相应工具完成。

欢迎通过 [Issue](https://github.com/CalBill/research-prose-zh/issues) 提交具体原句、修改结果及读感反馈。更新优先解决实际出现的问题，保留原本通顺的表达，不把个别问题词扩大成全局禁词。

---

<div align="center">

<strong>把对象说清，把关系写顺，让一段话完整地展开。</strong><br>
<sub><a href="./SKILL.md">阅读规则</a> · <a href="./references/examples.md">查看示例</a> · <a href="./LICENSE">MIT License</a></sub>

</div>
