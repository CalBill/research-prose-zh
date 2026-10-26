# 中文文档表达

用于中文文档起草、改写和润色的 Agent Skill。适用于 Word、WPS、飞书、Markdown 等载体，也适用于直接在聊天中交付的文档草稿。

重点是措辞自然、关系清楚、段落连贯。修改时保留事实、归因、实质条件和论证关系，删除没有额外信息的防御性说明，调整生硬的抽象措辞，避免为了压缩文字而损失自然搭配。

当前版本为 v0.2，由范文观察、实际改稿和用户反馈整理而成，仍在迭代。它提供写作指令和示例，未训练或微调模型。文件生成、排版和平台操作由相应工具完成。

## 文件结构

```text
research-prose-zh/
├── SKILL.md                  主规则和适用范围
├── agents/openai.yaml        Codex 的显示名称与默认提示
├── references/examples.md    改写示例与编辑判断
└── references/calibration.md 样本校准和规则更新方法
```

## 在 Codex 中安装

将本仓库克隆到用户级技能目录。访问私有仓库时，需要先登录具有读取权限的 GitHub 账号：

```sh
mkdir -p ~/.agents/skills
gh repo clone CalBill/research-prose-zh ~/.agents/skills/research-prose-zh
```

在后续任务中可以明确调用：

```text
请使用 $research-prose-zh，修改下面这段文档正文。
```

如需在所有项目的文档任务中默认使用，将下面的要求追加到 `~/.codex/AGENTS.md`，保留该文件已有的其他规则：

```text
起草、改写或润色中文文档正文时，先读取并遵循
~/.agents/skills/research-prose-zh/SKILL.md，按需要读取其中链接的示例。
适用于 Word、WPS、飞书、Markdown 等载体及聊天中交付的文档草稿，
无需用户再次指定文风。日常聊天、纯格式转换和仅排版任务不默认采用；
用户明确指定其他文风时，按其要求调整。
```

新任务会读取全局指令。若技能列表未显示新安装的 Skill，可重启 Codex。加载机制见 [Codex 技能说明](https://learn.chatgpt.com/docs/build-skills)和[全局指令说明](https://learn.chatgpt.com/docs/agent-configuration/agents-md)。

## 在其他 Agent 中使用

支持 `SKILL.md` 的 Agent 可以读取整个文件夹，具体安装位置按目标工具要求设置。没有技能机制时，可要求 Agent 在写文档前读取主规则，并在需要时读取示例。

若希望默认用于文档任务，还需将调用要求加入该 Agent 的长期指令。`agents/openai.yaml` 是 Codex 配置，其他工具按自身格式处理。

## 后续更新

优先记录具体原句、修改结果和读感反馈，再调整对应规则。保留原本通顺的表达，不把少数问题词扩大成全局禁词，也不以句子更短作为修改是否有效的唯一标准。
