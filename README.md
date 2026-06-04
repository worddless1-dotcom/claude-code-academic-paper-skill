# AI 论文助手 — Claude Code 学术论文自动化写作 Skill

一键从文献检索到论文成稿，全流程自动化。

## 效果展示

输入研究主题，自动完成：

```
文献检索（Google Scholar + 知网） → 文献筛选分类 → 论文结构确定 → 逐节撰写 → DOCX 生成 → 质量检查
```

支持论文类型：综述、IMRAD 实验论文、学位论文章节、会议论文、技术报告。

## 功能特点

- **自动文献检索**：通过浏览器自动化搜索 Google Scholar 和知网，自动记录元数据
- **智能结构规划**：根据文献主题聚类自动确定论文章节，不套模板
- **全流程写作**：逐节撰写，自动引用文献，保持学术风格
- **DOCX 生成**：自动排版（宋体正文、黑体标题、A4 页面）
- **质量把关**：模拟审稿人检查，确保无关键问题
- **定时推进**：设置后自动从头跑到尾，无需手动干预

## 安装

### 前提条件

- 已安装 [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
- 已安装 [chrome-devtools MCP](https://github.com/anthropics/anthropic-quickstarts/tree/main/anthropic-mcp-servers)（用于浏览器自动化检索）

### 安装 Skill

```bash
# 克隆仓库
git clone https://github.com/worddless1-dotcom/claude-code-academic-paper-skill.git

# 将 skill 复制到 Claude Code 的 skills 目录
cp -r claude-code-academic-paper-skill/paper-writing ~/.claude/skills/
```

或直接在 Claude Code 中使用：

```
/install-skill https://github.com/worddless1-dotcom/claude-code-academic-paper-skill
```

## 使用方法

在 Claude Code 中输入：

```
/paper-writing
```

然后按提示输入：
- 研究主题
- 目标读者
- 语言（中文/英文）
- 字数目标
- 检索关键词

之后全自动运行，最终在 `output/` 目录生成论文 DOCX。

## 工作流程

| 阶段 | 内容 | 自动化 |
|------|------|--------|
| Step 0 | 收集基本信息 | 交互式 |
| Phase 1 | 研究规划（检索策略、纳入/排除标准） | 自动 |
| Phase 2 | 英文文献检索（Google Scholar） | 自动 |
| Phase 3 | 中文文献检索（知网） | 自动 |
| Phase 4 | 文献筛选分类 + 确定论文结构 | 自动 |
| Phase 5 | 论文逐节撰写 | 自动 |
| Phase 6 | DOCX 生成 | 自动 |
| Phase 7 | 质量检查 | 自动 |

## 必需依赖

以下 skill 需要提前安装：

- `doc-coauthoring` — 协助论文撰写和结构规划
- `academic-paper-reviewer` — 模拟审稿人进行质量检查
- `docx` — DOCX 文件生成和排版

## 常见问题

**Q: 知网检索需要什么？**
A: 需要你提前在浏览器登录高校/机构账号，skill 会自动操作已登录的知网页面。

**Q: 论文质量怎么样？**
A: Skill 内置了严格的质量门槛，每个阶段必须达标才能进入下一阶段。但 AI 生成的内容仍需人工审核和修改。

**Q: 支持英文论文吗？**
A: 支持。在启动时选择英文语言即可。

## 许可证

MIT License

## 欢迎贡献

Issues 和 Pull Requests 均欢迎！
