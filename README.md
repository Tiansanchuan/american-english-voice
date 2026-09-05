# American English Voice

用于美式英语口语陪聊的插件。围绕你选择的话题自然聊天，简短纠正语法，帮助组织表达，并在能够实际听到音频时提供发音反馈。

练习规则：[SKILL.md](skills/american-english-conversation/SKILL.md)。

## 从 GitHub 安装

仓库地址：<https://github.com/Tiansanchuan/american-english-voice>

本仓库同时包含插件和 marketplace 清单，可作为 GitHub 插件来源导入。

### Codex

在终端添加来源：

```sh
codex plugin marketplace add https://github.com/Tiansanchuan/american-english-voice.git
```

随后打开插件目录，选择 **American English Voice** 来源并安装同名插件。安装后开始一个新会话，让新会话加载插件。

如果界面提供“添加 marketplace / GitHub 来源”入口，填写上面的仓库地址。不要填写单个文件、ZIP 下载或 `tree/main` 页面地址。

### ChatGPT 工作区导入

拥有工作区管理员权限时，可在 **Admin → Plugins → Add → Import marketplace** 中填写：

- Source：`https://github.com/Tiansanchuan/american-english-voice`
- Path：留空，marketplace 位于仓库根目录下的标准位置。
- Branch：`main`。

导入后根据界面提示安装插件。个人账号、手机端和不同产品界面的导入能力可能不同；GitHub 发布本身不保证手机 Voice 能加载或延续技能规则，这部分仍需实测。

官方参考：[插件打包与 GitHub 来源](https://developers.openai.com/plugins/build/plugins)、[工作区导入](https://learn.chatgpt.com/docs/enterprise/plugin-management)。

## 开始练习

在能够使用该插件的会话中明确请求：

> Start practicing American English with me through conversation in ChatGPT Voice.

也可以说：“开始和我用 ChatGPT Voice 练习美式英语。”你可以先在文字中启动，再尝试在同一聊天中切换 Voice。切换后的规则延续需要在你的实际客户端验证。

- 默认使用英语；明确要求中文解释时才使用中文。
- 小语法错误简短纠正后继续聊天，不要求重说。
- 表达明显不自然、卡住或出现清晰的发音问题时，提供针对性的帮助并邀请重说。
- 普通停顿会留出思考空间，不设置固定课程、评分或重试次数。
- 说“退出练习”或“exit practice”结束纠错模式。

只有能实际听到音频时才判断发音；仅有文字时不会声称听到了发音错误。

## 文件结构

```text
.agents/plugins/marketplace.json
.codex-plugin/plugin.json
skills/american-english-conversation/
  SKILL.md
  agents/openai.yaml
```

仓库根目录就是插件根目录。Marketplace 中的 `source.path` 为 `./`，插件清单中的 `skills` 为 `./skills/`。即使通过 GitHub 导入，同一仓库内的插件仍使用 `"source": "local"`。

## 后续更新

在本仓库的 `skills/` 中修改练习规则，在 `.codex-plugin/plugin.json` 中修改插件信息。修改后提交并推送到 GitHub。

Codex 可以刷新来源：

```sh
codex plugin marketplace upgrade american-english-voice
```

随后在插件目录检查更新或重新安装，并在新会话中使用。工作区管理员也可以在 marketplace 管理页面选择 **Sync now**。
