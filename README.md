# OpenClaw 技能验收 / OpenClaw Skill Acceptance

面向 OpenClaw skill 的发布前验收与放行检查。  
Pre-release acceptance and release-gating checks for OpenClaw skills.

`openclaw-skill-acceptance` 是一个用于发布把关的 OpenClaw skill。适用于新建或更新后的 skill 在内部上线或发布到 ClawHub 之前做基于证据的验收。默认输出不是聊天摘要，而是一份严格的企业级 Markdown 验收报告。  
`openclaw-skill-acceptance` is an OpenClaw skill for release gating. It is designed for evidence-based acceptance before a new or updated skill is rolled out internally or published to ClawHub. Its default output is not a casual chat summary, but a strict enterprise-style Markdown acceptance report.

## 简短说明 / Short Description

适用于新建或更新后的 OpenClaw skill 在内部发布或 ClawHub 发布前进行验收验证。  
Use this skill to validate a new or updated OpenClaw skill before internal rollout or ClawHub publication.

## 市场简介 / Marketplace Summary

这个 skill 用来判断一个 OpenClaw skill 是否真的具备发布条件。它检查的不只是“能不能被加载”，还会覆盖触发描述质量、元数据规范、资源组织、证据纪律、动态行为、依赖风险，以及报告完整性。最终结果会给出结构化的企业级验收报告，并明确标注 `通过`、`有条件通过` 或 `不通过`，同时附带发布建议。  
This skill is used to determine whether an OpenClaw skill is actually ready for release. It checks more than simple loadability. It also reviews trigger quality, metadata hygiene, resource organization, evidence discipline, runtime behavior, dependency risk, sensitive capabilities, auto-execution risk, hidden or obfuscated content, and report completeness. The final result is a structured enterprise-style acceptance report with explicit business and integration conclusions, plus release guidance.

## 检查范围 / What It Checks

- 检查 `SKILL.md`、命名、描述风格和元数据是否符合规范
- 审核触发设计、渐进式加载、资源布局和指令边界等最佳实践
- 提取功能清单并评估覆盖情况
- 通过 `openclaw gateway restart`、`openclaw skills list`、`openclaw skills info` 做加载验证
- 使用正向、负向、不完整输入和安全用例做动态验证
- 检查 grouped skills 的依赖与冲突风险
- 审计命令执行、本地敏感文件访问、宽范围 HTTP 调用等敏感能力
- 检查 hooks、动态注入、加载即执行命令等自动执行风险
- 检查隐藏内容、混淆内容、编码载荷、零宽字符和安全策略覆盖迹象
- 检查声明能力与实际能力是否存在偏差
- 支持批量筛查模式，用于先做多 skill 风险分拣，再决定哪些进入深度验收
- 在边界结论场景下可选做二次模型复核
- 基于真实证据生成报告，并将环境问题与 skill 缺陷分开记录
- 给出内部发布或 ClawHub 发布建议

- Validates `SKILL.md`, naming, description style, and metadata quality
- Audits trigger design, progressive loading, resource layout, and instruction boundaries
- Extracts the functional surface area and evaluates coverage
- Verifies loading with `openclaw gateway restart`, `openclaw skills list`, and `openclaw skills info`
- Runs positive, negative, incomplete-input, and safety test cases
- Checks grouped-skill dependency and conflict risk
- Audits sensitive capabilities such as command execution, local sensitive-file access, and broad HTTP reach
- Checks hooks, dynamic injection, and load-time execution behavior
- Checks hidden content, obfuscated payloads, zero-width characters, and safety-override traces
- Checks whether the declared capability scope matches the actual reachable power
- Supports batch triage before deep acceptance when multiple skills need screening
- Allows optional second-opinion review when the conclusion sits near a release boundary
- Produces a report grounded in real evidence while separating environment noise from skill defects
- Provides a release recommendation for internal rollout or ClawHub publication

## 默认输出 / Default Output

默认输出是一份企业级 Markdown 验收报告，而不是简单的聊天回复。  
The default output is an enterprise-style Markdown acceptance report, not a simple chat reply.

报告通常包含这些部分：  
The report usually includes:

- 执行摘要
- 业务能力结论与平台集成结论
- 风险摘要卡
- 敏感能力审计与权限-用途匹配检查
- 自动执行与隐藏内容检查
- 覆盖矩阵与覆盖判定
- 可选二次模型复核记录
- 文档信息
- 目标 skill 与工作区信息
- 规范检查结果
- 最佳实践审计结果
- 静态与动态验证结果
- 环境问题
- 最终结论
- 发布建议
- 后续行动项

- Document information
- Executive summary
- Separate business and platform/integration conclusions
- Sensitive-capability audit and permission-to-purpose fit check
- Coverage matrix with explicit coverage states
- Target skill and workspace context
- Compliance check results
- Best-practice audit results
- Static and dynamic validation results
- Environment issues
- Final conclusion
- Release recommendation
- Follow-up action items

## 适用场景 / When To Use

- 新 skill 首次发布前做验收
- 已修改 skill 在重新发布前做回归检查
- 判断 skill 是否适合内部上线
- 判断 skill 是否适合发布到 ClawHub

- Acceptance before the first release of a new skill
- Regression validation before re-releasing an updated skill
- Deciding whether a skill is ready for internal rollout
- Deciding whether a skill is ready for ClawHub publication

## 不适用场景 / When Not To Use

- 与 OpenClaw skill 无关的普通 prompt 试验
- 没有证据记录的一次性聊天测试
- 与 skill 包无关的自由式代码审查
- 在验收过程中自动修改目标 skill

- General prompt experiments unrelated to OpenClaw skills
- One-off chat tests without evidence capture
- Free-form code review unrelated to a skill package
- Automatically modifying the target skill during acceptance

## 示例提示词 / Example Prompt

```text
使用 $openclaw-skill-acceptance 对这个 OpenClaw skill 做发布验收，执行规范检查、最佳实践审计、正向/负向/不完整输入/安全用例测试，并生成企业级验收报告。
```

```text
Use $openclaw-skill-acceptance to run release acceptance for this OpenClaw skill, including compliance checks, best-practice auditing, positive/negative/incomplete-input/safety tests, and generation of an enterprise-style acceptance report.
```

## 列表页文案 / Listing Copy

### 一句话介绍 / One-Line Intro

面向 OpenClaw skill 的发布前验收工具，提供基于证据的动态验证与企业级报告。  
Pre-release acceptance for OpenClaw skills with evidence-based runtime validation and enterprise-style reporting.

### 短介绍 / Short Intro

在发布前验证 OpenClaw skill，覆盖规范检查、功能覆盖、动态验证与结构化企业报告。  
Validate an OpenClaw skill before release with compliance checks, functional coverage review, runtime validation, sensitive-capability auditing, and structured enterprise reporting.

### 完整介绍 / Full Intro

`openclaw-skill-acceptance` 适合那些需要真实发布结论，而不是随意意见的 OpenClaw skill 作者。它会从规范、最佳实践、功能覆盖、grouped skill 依赖风险、可加载性和运行时行为多个维度验证 skill。除了常规验收，它还会单独暴露命令执行、本地敏感文件访问、动态注入、hooks、隐藏内容与混淆载荷等风险信号；当一次性要筛查多个 skill 时，也支持先做批量分拣，再对高风险或边界结果的 skill 进入深度验收。它要求真实证据，保留待验证项，区分环境噪音与 skill 缺陷，并最终生成一份带发布建议的企业级 Markdown 验收报告，用于内部上线或 ClawHub 发布决策。  
`openclaw-skill-acceptance` is for OpenClaw skill authors who need a real release decision rather than a casual opinion. It evaluates a skill across compliance, best practices, feature coverage, grouped-skill dependency risk, loadability, runtime behavior, and sensitive-capability exposure. Beyond ordinary acceptance, it also surfaces command execution, local sensitive-file access, dynamic injection, hooks, hidden content, and obfuscated payloads as first-class risk signals. When many skills need screening, it can also support batch triage first and reserve deep acceptance for risky or boundary-case skills. It requires real evidence, keeps static-only findings distinct from dynamic coverage, separates environment noise from skill defects, and makes permission-to-purpose mismatches visible in the final enterprise-style Markdown acceptance report.
