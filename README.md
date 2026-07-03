# Codex Resume PDF

一个基于 Codex 工作流的开源简历项目：先把你的简历内容整理成 Markdown，再参考现有设计模板生成 HTML，最后导出为 PDF。

## 这个项目能做什么

- 使用 `examples/profile.md` 作为 Markdown 简历样例
- 使用 `examples/resume.html` 和 `examples/resume-llm.html` 作为模板参考
- 使用 Chromium headless 将 HTML 导出为 PDF
- 把用户生成的最终文件统一放到 `output/`

## 使用方式

1. 在项目根目录打开 Codex。
2. 直接粘贴你的简历内容，或者让 Codex 先帮你生成一份 `profile.md`。
3. 让 Codex 阅读 `resume_design_summary.md`，并参考 `examples/` 下的样例生成简历页面。
4. 让 Codex 把生成结果输出到 `output/`：
   - `output/profile.md`
   - `output/*.html`
   - `output/*.pdf`

## 手动导出 PDF

如果已经有 HTML 文件，可以直接用 Chromium 导出：

```bash
chromium --headless --disable-gpu \
  --print-to-pdf=output/resume.pdf \
  file:///absolute/path/to/output/resume.html
```

示例文件导出命令：

```bash
chromium --headless --disable-gpu \
  --print-to-pdf=examples/resume.pdf \
  file:///home/tony/Documents/profile/examples/resume.html

chromium --headless --disable-gpu \
  --print-to-pdf=examples/resume-llm.pdf \
  file:///home/tony/Documents/profile/examples/resume-llm.html
```

## 项目结构

```text
.
├── AGENTS.md
├── examples/
│   ├── profile.md
│   ├── resume.html
│   └── resume-llm.html
├── output/
├── resume_design_summary.md
└── README.md
```

## 说明

- `resume_design_summary.md` 记录了当前简历模板的设计思路
- `examples/` 中的示例数据已经做过脱敏处理，可直接公开
- 这是一个轻量项目，重点是让 Codex 接管“简历整理 -> 页面生成 -> PDF 导出”的流程

## License

MIT
