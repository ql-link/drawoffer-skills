<div align="center">

# DrawOffer Skills

**Resume and job-search Agent Skills: diagnosis, rewriting, drafting, translation, interview prep and career planning**

Write resumes from facts: only your real experience, no invented numbers or responsibilities, and every change goes to you for approval first.

<p>
  <a href="./LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-3f6fd8?style=flat-square"></a>
  <a href="https://www.drawoffer.com/en"><img alt="DrawOffer" src="https://img.shields.io/badge/Try-drawoffer.com-3f6fd8?style=flat-square"></a>
</p>

<p>
  <a href="https://www.drawoffer.com/en"><strong>Try DrawOffer</strong></a> ·
  <a href="#install">Install</a> ·
  <a href="#skills">Skills</a> ·
  <a href="./README.md">简体中文</a>
</p>

</div>

---

These are the resume-writing methods that [DrawOffer](https://www.drawoffer.com/en), an AI resume builder, uses in production, packaged as 11 Agent Skills you can install in Claude Code and other AI assistants. Once installed, ask "review my resume", "rewrite this internship with STAR" or "translate my resume into English", and the assistant follows the matching method.

The skill text is written in Chinese and tuned for Chinese resumes and the Chinese job market, but the methods (STAR, XYZ, evidence rules) apply to resumes in any language.

Every skill shares one [evidence method](./skills/resume-evidence-method/SKILL.md):

- **Facts only.** Conclusions rest on the resume text, the job description and materials you provide, and facts you add in the conversation.
- **Nothing invented.** No made-up company details, team sizes, technologies or numbers. Without data, it describes verifiable deliverables instead.
- **No inflated roles.** "Took part in" never becomes "led".
- **You approve every change.** Each edit comes with its location in the resume and a reason.

## Install

### Claude Code

```text
/plugin marketplace add ql-link/drawoffer-skills
/plugin install drawoffer@drawoffer-skills
```

Skills then trigger from natural requests, or you can call one directly, such as `/drawoffer:resume-diagnosis`.

### Install only some skills

Copy the folders you want into `~/.claude/skills/` (all projects) or a project's `.claude/skills/`:

```bash
git clone https://github.com/ql-link/drawoffer-skills.git
cp -r drawoffer-skills/skills/resume-diagnosis ~/.claude/skills/
cp -r drawoffer-skills/skills/resume-evidence-method ~/.claude/skills/
```

Install `resume-evidence-method` alongside the others; they reference its rules.

### Other assistants

Each `SKILL.md` is plain Markdown using only the portable `name`, `description`, `license` and `metadata` fields. In tools without Skills support, use the body as a system prompt.

## Skills

| Skill | What it does |
|---|---|
| [resume-diagnosis](./skills/resume-diagnosis/SKILL.md) | Reviews a resume as a recruiter and interviewer would: full review, single-entry deep dive, job-description match, structure check, snippet feedback |
| [resume-evidence-method](./skills/resume-evidence-method/SKILL.md) | Shared evidence rules and a six-level issue priority used by every skill |
| [resume-edit-workflow](./skills/resume-edit-workflow/SKILL.md) | Chooses the right kind of edit and keeps changes in scope |
| [resume-edit-local](./skills/resume-edit-local/SKILL.md) | Polishes one field, one bullet or one sentence |
| [resume-edit-entry-star](./skills/resume-edit-entry-star/SKILL.md) | Restructures a whole experience entry with STAR |
| [resume-generate-from-materials](./skills/resume-generate-from-materials/SKILL.md) | Drafts a new entry from materials you provide |
| [resume-guided-creation](./skills/resume-guided-creation/SKILL.md) | Walks a first-time student through writing a first resume |
| [resume-translation](./skills/resume-translation/SKILL.md) | Translates the whole resume faithfully and keeps the original |
| [resume-title-generator](./skills/resume-title-generator/SKILL.md) | Suggests short, distinguishable resume titles |
| [interview-guide](./skills/interview-guide/SKILL.md) | Interview prep and review: likely follow-up chains, STAR answer outlines, questions to ask |
| [career-planning](./skills/career-planning/SKILL.md) | Career direction, skill gaps and a 2–4 week action plan |

## The full product

These skills cover how to write. [DrawOffer](https://www.drawoffer.com/en) adds resume import from PDF, Word and Markdown, templates with PDF export, tailoring to job descriptions, AI mock interviews and an application tracker. Resume editing, export and the job board are free.

## License

[MIT](./LICENSE) © 2026 ql-link

Parts of the skills are adapted from [HireTechUpUp/resume-agent-prompts](https://github.com/HireTechUpUp/resume-agent-prompts) (MIT). See [THIRD_PARTY_NOTICES.md](./THIRD_PARTY_NOTICES.md).
