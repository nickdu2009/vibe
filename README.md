# Vibe Coding · 内部分享 PPT

一份用前端技术（reveal.js + 自定义主题）实现的 web PPT，内容是 Vibe Coding 方法论与 5 个真实项目的实践复盘。

> **作者**：Nick Du · 2026 内部分享

---

## 一分钟启动

无需 build，无需 npm install——纯静态文件，开个本地 HTTP server 就能放映。

```bash
# 进入工作目录
cd /Users/duxiaobo/workspaces/nickdu/vibe

# 启动本地 HTTP server（任选其一）
python3 -m http.server 7788
# 或者：
npx serve -l 7788

# 打开浏览器，按 F11 进入全屏播放
open "http://localhost:7788"
```

> 推荐用 **Chrome / Safari** 16:9 全屏播放，效果最佳。

---

## 演讲控制

| 操作 | 快捷键 |
|------|--------|
| 下一页 | `→` / `Space` / `N` |
| 上一页 | `←` / `P` |
| 跳转到第 N 页 | 输入数字 + `Enter` |
| 全屏 | `F` |
| 演讲者备注（双屏） | `S` |
| 概览模式 | `ESC` |
| 暂停黑屏 | `B` |

---

## 文件结构

```
vibe/
├── index.html          # 主入口 · 全部 30 张幻灯片
├── styles.css          # 自定义深色主题（电紫 / 青 / 玫红渐变）
└── README.md           # 本说明
```

外部依赖通过 CDN 加载，**无离线运行能力**：

- `reveal.js@5.1.0` — 演示框架
- `mermaid@10` — 流程图（worktrail 知识生命周期那一页）
- `Inter` + `JetBrains Mono` — Google Fonts

如需离线，下载这三类资源到本地并改成相对路径即可。

---

## 内容大纲（30 页）

### Part 0 · 开场（2 页）
1. 封面
2. Agenda — 今天你会带走什么

### Part 1 · 什么是 Vibe Coding（3 页）
3. Section divider
4. 重新定义：✕ 它不是 / ✓ 它是
5. 从 Chat 到 Workflow 的 7 维转变

### Part 2 · 方法论 5 大支柱（7 页）
6. Section divider
7. 5 Pillars 总览
8. ① Context First — 别让 AI 重新认识项目
9. ② Skill-Driven Discipline
10. ③ Review Loop · 五分型
11. ④ Multi-Agent Parallelism
12. ⑤ Handoff & State

### Part 3 · 工具集（6 页）
13. Section divider
14. Skills 管纪律 · Worktrail 管记忆（左右脑）
15. agent-skills · 14 个 Skill 一览
16. agent-skills 设计哲学
17. worktrail · 知识生命周期（含 Mermaid）
18. worktrail 反功能清单

### Part 4 · 5 个实战项目（7 页）
19. Section divider
20. 5 项目总览 + 数据看板
21. Case 1 · COI Forge
22. Case 2 · Delivery Experts
23. Case 3 · Goto（双轨 API 迁移）
24. Case 4 · Template-Unify（AI 嵌入产品）
25. Case 5 · Consumer Finance（PromptSpeed）

### Part 5 · 经验与展望（5 页）
26. Section divider
27. 7 条带血的踩坑教训
28. 7 句方法论金句
29. Vibe Coding 2.0 展望
30. Thanks · Q&A

---

## 自定义与扩展

### 改一句话/数据
直接改 `index.html`，按 `Cmd+R` 刷新浏览器即可——reveal.js 是纯前端，无需重启。

### 加一张新 slide
在 `index.html` 中 `<div class="slides">` 下加一个 `<section>...</section>`。常用模板：

```html
<section class="slide-content">
  <div class="slide-header">
    <span class="num">XX</span>
    <span class="kicker">Kicker</span>
  </div>
  <h2>页面标题 · <span class="gradient-cool">副标题</span></h2>
  <div class="glow-line"></div>
  <!-- 内容 -->
</section>
```

### 主题调色
所有颜色集中在 `styles.css` 顶部 `:root` CSS 变量：

```css
--accent: #7c5cff;       /* electric purple */
--accent-2: #00d4ff;     /* cyan */
--accent-3: #ff5cae;     /* magenta */
--accent-4: #5cffb1;     /* mint */
```

### 导出 PDF
Chrome 打开 PPT 后追加 `?print-pdf` 查询参数：

```
http://localhost:7788/index.html?print-pdf
```

然后 `Cmd+P` → 选择 "另存为 PDF"，每页一张幻灯片。

---

## 风格说明

- **不用图片，全部 CSS 绘制**：保证整套 PPT 不到 80KB，可邮件附件级分享。
- **Inter + JetBrains Mono**：现代终端风，与代码契合。
- **网格背景 + 双色渐变光晕**：科技感不浮夸。
- **Mermaid 流程图主题色**与全局 CSS 变量同步。

---

## 演讲建议时长

| 篇幅 | 建议时长 |
|------|----------|
| 完整 30 页 | 30–40 分钟（含 5 分钟 Q&A） |
| 精简版（跳过 Part 1 + 5 案例 → 3） | 15–20 分钟 |
| Lightning（仅 Part 2 + 总览） | 8–10 分钟 |

可在播放时按 `B` 暂时黑屏跳过某页，或 `ESC` 进入概览模式直接选页。

---

## TL;DR — 这套 PPT 想表达的核心

> Vibe Coding 不是「让 AI 写代码」，是<br/>
> **让每一步可验证、可交接、可审查的工程文化转变**。
>
> Skills 管纪律 · Worktrail 管记忆 — 这是 Vibe Coding 的左右脑。
