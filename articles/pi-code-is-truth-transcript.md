# 文字实录：代码即真相，Bash 已足够

> Pi 两位作者访谈（英文原声，中英对照）。本文字稿根据视频自动字幕整理，英文为原话大意（自动识别可能存在个别不准确），中文为对应翻译。

---

## 一、代码即真相：编程不需要记忆系统

**英文原话：**

> "So for coding I don't want a memory system — code is truth. Code is the ground truth, and it's also evolving. I don't need another place that you need to maintain. The codebase itself is the source of truth."

> "Models are really good at kinda understanding code structure and the code style, just based on reading one or two files."

> "And if you've got a monorepo — you know, dozens of agents, forty-two folders, or whatever — you might give it a map of where things are, which is just the list of folders and short descriptions. That's fine, easy to maintain."

> "But claiming you need all that — using embeddings and using AST, all this stuff — I mean, if you wanna waste time... Pretty sure you've never done an evaluation that actually produces better outputs. Guarantee, it does not."

**中文翻译：**

> 「对于编程，我不想要记忆系统——代码即真相。代码就是基准事实，而且它还在不断演化。我不需要另一个需要维护的地方。代码库本身就是事实来源。」

> 「模型非常擅长理解代码结构和代码风格，仅仅基于读一两个文件就能做到。」

> 「如果你有一个 monorepo——几十个 agent、四十二个文件夹什么的——可以给它一张『哪里有什么』的地图，其实就是文件夹列表加简短描述。这没问题，容易维护。」

> 「但声称你需要那套东西——用 embeddings、用 AST 之类的——我是说，如果你想浪费时间的话……我很确定从来没有任何评估证明它能产生更好的输出。保证没有。」

---

## 二、Bash 就是一切所需

**英文原话：**

> "Around July, August, both me and Arlene actually discovered, through different means, that Bash is all you need — in the sense that models are inherently trained to use Bash. And Bash basically is a programming language, so they can just build their own stuff."

**中文翻译：**

> 「大概七八月的时候，我和 Arlene 通过不同的途径都发现：Bash 就是一切所需——因为模型天生就是被训练来用 Bash 的，而 Bash 本质上就是一种编程语言，所以模型可以直接用它构建自己的东西。」

---

## 三、MCP 与工具之争：可组合性才是关键

**英文原话：**

> "I have very useful data in Sentry. But I don't use Sentry for MCP... If it's gonna be a tool for my coding agents — 'okay, we need this data from Sentry, and we need it in a certain form' — let's build ourselves a skill. And the skill really is just like: here's a prompt that can load on demand, but also composes its own tools."

> "I think this sort of MCP versus tools situation is a little bit weird. At the end of the day, the file system and the tools themselves are one thing — but composability really is the key."

**中文翻译：**

> 「Sentry 里有非常有用的数据，但我不会用 MCP 去接 Sentry……如果它要成为我的 coding agent 的工具——『好，我们需要 Sentry 的数据，而且需要某种特定形式』——那我们就自己构建一个 skill。skill 其实就是一段可以按需加载的 prompt，同时它也能组合自己的工具。」

> 「我觉得 MCP 与工具之间的这种争论有点奇怪。归根结底，文件系统和工具本身是一回事——但可组合性才是关键。」

---

## 四、回到 Pi 的极简主义：上下文高效的 skill

**英文原话：**

> "I also have my own Slack bot — it's called Mom, Master of Mischief — because it has access to one of my services, and it has access to the entire history of every channel it's in. Basically by using a JSON file, an append-only log — questions, answers, or problems in the system's responses. And that basically gives infinite memory."

> "I think that loops back kinda together to Pi minimalism. The interesting part of using Pi, or using a very small model, is that it sort of extends itself as an example."

> "So it's basically just the idea of: how can you build skills in a very context-efficient way, so that you can combine them together with other things."

**中文翻译：**

> 「我也有自己的 Slack bot——它叫 Mom（Master of Mischief，捣蛋大师）——因为它能访问我的一个服务，能看到它所在每个频道的全部历史。基本上就是用一个 JSON 文件、一个 append-only 日志，把问题、答案、系统响应里的问题都记下来，这就相当于提供了无限记忆。」

> 「我觉得这又回到了 Pi 的极简主义。使用 Pi、或者说用一个很小的模型，有趣的地方在于：它本身就是『自我扩展』的一个例子。」

> 「所以核心思想就是：如何用非常上下文高效的方式构建 skill，让它们可以和其它东西互相组合。」

---

## 观点速记

- **代码即真相**：代码库是事实来源，模型读一两个文件就能理解结构，不需要记忆系统 / RAG / 嵌入 / AST。
- **Bash 已足够**：模型天生会用 Bash，Bash 是编程语言，可以任意组合。
- **可组合 > 协议**：与其纠结 MCP，不如构建按需加载、可组合的 skill。
- **极简主义**：小模型 + 精简工具 + 上下文高效，是 Pi 的设计哲学。
