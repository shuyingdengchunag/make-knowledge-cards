# make-knowledge-cards

## 项目解决什么问题

文章、教程和读书笔记往往混有背景说明、重复表述和关键概念，直接回看不容易找到复习重点。这个 Agent Skill 把原文整理成可单独复习的 Markdown 知识卡片，方便回顾关键知识和检验记忆。

## 主要功能

- **读取文本**：支持直接粘贴正文，或读取当前环境可访问的本地 Markdown（`.md`、`.markdown`）和 TXT（`.txt`）文件。
- **提炼与去重**：优先选取重要的定义、机制、判断标准或操作规则。每张卡片只讲一个知识点，保留原文中的适用条件和不确定性。
- **输出知识卡片**：每张包含标题、核心知识、简明解释，以及一个原文例子或一道可依据原文回答的自测题。通常输出 5～8 张，知识点不足时按实际数量输出。

当前版本的输入范围为上述文本。网页抓取、PDF 和 Word 文件读取、Anki 导出及独立图形界面暂未支持。

## 安装方法

以 Codex 为例，将本项目的 [`skills/make-knowledge-cards`](skills/make-knowledge-cards) 整个文件夹复制到你要使用它的工作目录下的 `.agents/skills/`，保留 `SKILL.md` 和 `agents/openai.yaml`，然后在该工作目录打开 Codex。

```text
.agents/skills/make-knowledge-cards/
├── SKILL.md
└── agents/
    └── openai.yaml
```

本 Skill 由说明文件和配置组成，无需另装运行依赖。其他支持 Agent Skills 的环境可按各自的方式导入同一文件夹。[Codex 官方安装目录说明](https://developers.openai.com/codex/skills)

## 使用方法

- **粘贴正文**：发送「使用 `$make-knowledge-cards`，把下面的文章整理成知识卡片」，并在同一条消息中粘贴正文。
- **读取本地文件**：发送「使用 `$make-knowledge-cards`，把 `./notes/reading.txt` 整理成知识卡片」。把示例路径换成当前环境可读取的实际文件路径。

## 输入输出示例

**输入**

```text
使用 $make-knowledge-cards，把下面的文字整理成知识卡片。

读书笔记按主题归档。同一主题的笔记放在同一个目录，方便集中查阅。
```

**输出示例**

### 读书笔记按主题归档

- **核心知识**：同一主题的读书笔记放在同一个目录。
- **简明解释**：按主题集中存放，方便查阅相关笔记。
- **自测问题**：同一主题的读书笔记应该放在哪里？
