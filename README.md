# MyYoda 内容仓库发布指南

「发现」面板的官方内容源。维护者按以下步骤发布与更新内容。

## 首次发布（一次性）

1. 创建公开仓库（已在本地准备好本目录）：

```bash
gh repo create GeoffBao/myyoda-content --public --description "MyYoda 官方内容源（发现面板）"
git init && git remote add origin https://github.com/GeoffBao/myyoda-content.git
git add -A && git commit -m "init: MyYoda 官方内容源"
git push -u origin main
```

2. 发布首个 Release 并上传视频：

```bash
# 视频文件建议使用 ASCII 文件名（URL 编码更稳）
cp "Agent的本质到底是什么.mp4" agent-essence.mp4
gh release create v1 agent-essence.mp4 --title "v1 初始内容" --notes "首版官方视频"
```

3. 开启 MyYoda 主仓库 Discussions（社区承载）：

```bash
gh api -X PATCH repos/GeoffBao/MyYoda -f has_discussions=true
```

默认板块即包含 Q&A / Show and tell / Announcements（slug: `q-a` / `show-and-tell` / `announcements`），与「发现」面板映射一致。

## 更新视频版本（日常流程）

1. 把新视频传为新的 Release 资产：

```bash
gh release create v2 agent-essence-v2.mp4 --title "v2 视频更新"
```

2. 修改 `content.json` 中对应条目：

- `version` 改成新值（如 `2026.9.1`）——只要与旧值不同，用户端即显示「更新」红点
- `video.url` 指向新 Release 资产地址
- `video.size` 改为新文件字节数（`wc -c <file>` 获取）

3. commit + push 到 `main`。用户下次打开应用即可看到「更新」标记。

## 新增其他内容

在 `items` 数组追加条目即可，四种类型：

| 类型 | 必填字段 | 说明 |
|------|---------|------|
| `video` | `video.url`（+`size`） | 应用内下载播放 |
| `article` | `contentUrl` | 指向本仓库 .md 的 raw 地址，应用内渲染 |
| `announcement` | `body` | markdown 短文本 |
| `link` | `url` | 点击跳系统浏览器 |

条目排序按 `publishedAt` 倒序展示。
