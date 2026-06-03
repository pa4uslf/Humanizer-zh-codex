# Humanizer-zh for Codex

一个 Codex skill，用来编辑中文文本，去除常见 AI 写作痕迹，让内容更自然、直接、具体。

## 来源

- 核心内容翻译自 [blader/humanizer](https://github.com/blader/humanizer/tree/main)
- 实用规则参考 [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)
- 原始观察来自维基百科 [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) 指南

## Codex Layout

```text
Humanizer-zh-codex/
├── skills/
│   └── humanizer-zh/
│       └── SKILL.md              # Codex skill instructions
├── plugin/
│   ├── .codex-plugin/
│   │   └── plugin.json           # Codex plugin manifest
│   └── skills/
│       └── humanizer-zh/
│           └── SKILL.md          # Skill copy for plugin packaging
├── README.md
└── LICENSE
```

## 安装

### 作为单个 skill 使用

把 skill 目录复制或链接到 Codex 的 skills 目录：

```bash
mkdir -p ~/.codex/skills
ln -s "$PWD/skills/humanizer-zh" ~/.codex/skills/humanizer-zh
```

如果你通过 dotfiles 管理 Codex 配置，请把 `skills/humanizer-zh/` 复制到对应的 Codex skills 包里，再按你的 dotfiles 流程同步。

### 作为 Codex plugin 使用

本仓库也提供 `plugin/.codex-plugin/plugin.json`，用于 Codex plugin packaging。manifest 指向 `plugin/skills/` 目录。

## 使用

可以用这些方式触发：

- `用 humanizer-zh 帮我把这段话去 AI 味`
- `把下面这段中文改得更自然`
- `审一下这段文案，去掉模板感`
- `让这段 AI 生成文本更像人写的`

默认情况下，skill 只返回改写后的文本。需要诊断、评分或逐条解释时，请在请求里明确说明。

## 能处理的问题

这个 skill 会重点识别和修复：

- 过度强调意义、遗产、趋势和宏大价值
- 宣传式语言、广告腔和空泛褒义词
- 模糊归因，例如"专家认为"、"行业报告显示"
- 三段式法则、否定式排比和公式化总结
- 机械连接词、AI 高频词和填充短语
- 破折号、粗体、表情符号和列表标题的过度使用
- 缺乏真实语气的平板表达

## 处理原则

改写时应保留原意、事实、数据、专有名词和语气边界。不要新增来源、指标、案例、承诺或未在原文出现的事实。

这个工具不是为了欺骗 AI 检测器，而是为了提升写作质量。最好的"去 AI 化"不是加口语词，而是让文字更具体、更克制，也更像真实作者在思考。

## 许可

遵循原项目许可。核心内容基于维基百科社区的观察和总结。
