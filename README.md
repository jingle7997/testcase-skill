# doc-based-testcase-generator

基于需求文档自动生成结构化测试用例的 Claude Code Skill。

## 功能简介

提供 PRD、需求说明或接口文档，自动运用系统化的测试设计方法（正向、反向、边界值、等价类、场景法等）生成高质量测试用例文档。

支持四种测试类型：
- **功能测试** — 业务流程、状态流转、角色权限
- **接口测试** — 参数校验、错误码覆盖、鉴权与幂等
- **性能测试** — RT/QPS 指标、稳态/峰值/长稳场景
- **自动化候选筛选** — 标记适合自动化的用例并给出实现建议

## 安装

### 方式一：CC Switch（推荐）

1. 打开 [CC Switch](https://github.com/farion1231/cc-switch)
2. 进入 Skills 面板
3. 添加本仓库的 GitHub URL
4. CC Switch 会自动扫描并发现 `doc-based-testcase-generator` 技能
5. 一键安装到 Claude Code / Codex / Gemini CLI 等工具

### 方式二：手动安装

将 `doc-based-testcase-generator/` 目录复制到 Claude Code 的技能目录：

```bash
# 个人级别（所有项目可用）
cp -r doc-based-testcase-generator ~/.claude/skills/

# 项目级别（仅当前项目可用）
cp -r doc-based-testcase-generator .claude/skills/
```

## 使用方法

安装后在 Claude Code 中直接对话即可触发，例如：

- "请根据下面这份 PRD 生成测试用例"
- "根据这份接口文档，帮我设计接口测试用例"
- "从这段需求说明里整理出测试用例"
- "按你熟悉的写法写一份测试用例"

如需指定格式，可以说 "参考用例模板" 来使用内置的 Excel 模板结构。

## 目录结构

```
doc-based-testcase-generator/
├── SKILL.md                 # 技能定义（核心文件）
├── assets/                  # 用例模板
│   └── 用例模板.xlsx
├── references/              # 各测试类型的设计标准
│   ├── api-testcases-standard.md
│   ├── functional-testcases-standard.md
│   ├── performance-testcases-standard.md
│   └── automation-testcases-standard.md
├── docs/                    # 示例输出
│   └── 登录功能测试用例_参考模板.md
└── scripts/                 # 辅助脚本
    └── export_login_testcases_to_excel.py
```

## 许可证

MIT
