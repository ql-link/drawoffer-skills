<div align="center">

# DrawOffer Skills

**简历与求职 Agent Skills · 诊断、改写、生成、翻译、面试准备与职业规划**

基于事实写简历：只用你的真实经历，不编造数字和职责，每处修改先给你确认。

<p>
  <a href="./LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-3f6fd8?style=flat-square"></a>
  <a href="https://www.drawoffer.com"><img alt="DrawOffer 职绘" src="https://img.shields.io/badge/在线体验-drawoffer.com-3f6fd8?style=flat-square"></a>
</p>

<p>
  <a href="https://www.drawoffer.com"><strong>在线体验</strong></a> ·
  <a href="#安装">安装</a> ·
  <a href="#skills-一览">Skills 一览</a> ·
  <a href="./README.en.md">English</a>
</p>

</div>

---

这是 [DrawOffer 职绘](https://www.drawoffer.com) 在产品里实际使用的简历写作方法，整理成 11 个可以直接装进 Claude Code 等 AI 助手的 Agent Skills。装好之后，对 AI 说"帮我看看简历""这段实习按 STAR 改一下""把简历翻译成英文"，它会按对应的方法来做。

所有 Skill 共用一套 [简历证据方法](./skills/resume-evidence-method/SKILL.md)：

- **只用事实**：结论只建立在简历原文、你提供的岗位描述与资料、你在对话里补充的事实上。
- **不编造**：不替你补公司业务、团队规模、技术细节或数字；没有数据就写可核实的交付物。
- **不升级职责**：参与、协助不会被改成主导、负责。
- **先确认再改**：每处修改都附原文位置和理由，你确认后才算改动。

## 安装

### Claude Code（推荐）

在 Claude Code 里依次运行：

```text
/plugin marketplace add ql-link/drawoffer-skills
/plugin install drawoffer@drawoffer-skills
```

装好后可以直接用自然语言触发，也可以用 `/drawoffer:resume-diagnosis` 这样的命令手动调用。

### 只装其中几个

把需要的 Skill 文件夹复制到 `~/.claude/skills/`（对所有项目生效）或项目里的 `.claude/skills/`：

```bash
git clone https://github.com/ql-link/drawoffer-skills.git
cp -r drawoffer-skills/skills/resume-diagnosis ~/.claude/skills/
cp -r drawoffer-skills/skills/resume-evidence-method ~/.claude/skills/
```

`resume-evidence-method` 是其他 Skill 引用的基础规则，建议一起装。

### 其他 AI 助手

每个 `SKILL.md` 都是普通 Markdown，只使用通用的 `name`、`description`、`license`、`metadata` 字段。不支持 Skills 的工具，可以把正文直接作为系统提示词使用。

## Skills 一览

### 分析与诊断

| Skill | 做什么 | 这样说就会触发 |
|---|---|---|
| [resume-diagnosis](./skills/resume-diagnosis/SKILL.md) | 以招聘方和面试官视角分析简历：整体诊断、单段深挖、JD 匹配、结构审查、片段评价 | "帮我看看简历""和这个岗位匹配吗" |
| [resume-evidence-method](./skills/resume-evidence-method/SKILL.md) | 所有 Skill 共用的证据规则和六级问题优先级 | "这样写会不会夸大""怎么量化" |

### 修改与生成

| Skill | 做什么 | 这样说就会触发 |
|---|---|---|
| [resume-edit-workflow](./skills/resume-edit-workflow/SKILL.md) | 判断该用哪种修改方式，控制改动范围 | "改一下简历""优化这段" |
| [resume-edit-local](./skills/resume-edit-local/SKILL.md) | 润色一个字段、一条 bullet 或一句话 | "润色这句""改得专业一点" |
| [resume-edit-entry-star](./skills/resume-edit-entry-star/SKILL.md) | 按 STAR 重组一整段经历 | "这段实习按 STAR 改一下" |
| [resume-generate-from-materials](./skills/resume-generate-from-materials/SKILL.md) | 根据你提供的资料新写一段经历 | "把这个项目写进简历" |
| [resume-guided-creation](./skills/resume-guided-creation/SKILL.md) | 带第一次写简历的学生从零写出第一版 | "我没写过简历""应届生简历怎么写" |
| [resume-translation](./skills/resume-translation/SKILL.md) | 整份简历忠实翻译，保留原稿 | "把简历翻译成英文" |
| [resume-title-generator](./skills/resume-title-generator/SKILL.md) | 给简历起可辨识的标题 | "这份简历叫什么好" |

### 面试与规划

| Skill | 做什么 | 这样说就会触发 |
|---|---|---|
| [interview-guide](./skills/interview-guide/SKILL.md) | 面试准备与复盘：追问链预测、STAR 回答骨架、反问清单 | "帮我准备面试""面试官会问什么" |
| [career-planning](./skills/career-planning/SKILL.md) | 职业方向、能力差距和 2–4 周行动计划 | "我适合做什么""想转行到 X" |

## 用法示例

```text
帮我看看这份简历，我想投后端开发实习
```

AI 会先确定目标方向和求职阶段，再给出"一句总体判断 + 三到五条按影响排序的发现"，每条都带原文摘录、问题原因和改写示例。

```text
第二段实习写得太散了，按 STAR 帮我重写
```

AI 会重组这段经历的摘要和 bullet，不改动其他经历；缺少关键事实时，只问你一个具体问题，不会自己补。

## 想要完整的产品体验？

这些 Skills 只负责"怎么写"。[DrawOffer 职绘](https://www.drawoffer.com) 在此基础上提供：

- 导入 PDF / Word / Markdown 简历，自动识别模块后直接编辑；
- 中文简历模板与排版，导出 A4 分页或智能一页 PDF；
- 按岗位 JD 改简历，逐条对照要求；
- AI 模拟面试与复盘、求职进度看板。

简历编辑、导出和岗位看板免费使用。

## 参与贡献

欢迎提 Issue 和 PR：发现某个 Skill 的规则在实际使用中不好用、触发不准，或者有更好的写法，都可以直接提出来。修改时请保持"只用事实、不编造、不升级职责"这几条底线。

## 许可证

[MIT](./LICENSE) © 2026 ql-link

部分 Skill 的写法改编自 [HireTechUpUp/resume-agent-prompts](https://github.com/HireTechUpUp/resume-agent-prompts)（MIT），详见 [THIRD_PARTY_NOTICES.md](./THIRD_PARTY_NOTICES.md)。
