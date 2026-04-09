# `<skill-name>` 功能测试与验收记录（企业版）

> 关联 skill：`<skill-path>`

## 0. 执行摘要

| 项目 | 内容 |
|---|---|
| 业务能力结论 | `<pass-or-conditional-or-fail>` |
| 平台集成结论 | `<pass-or-conditional-or-fail>` |
| 发布建议 | `<internal-clawhub-or-fix-first>` |
| 动态覆盖率摘要 | `<dynamic-covered>/<feature-count>` |
| 关键未决项 | `<top-open-items>` |

```text
<executive-summary>
```

## 1. 文档信息

| 项目 | 内容 |
|---|---|
| 文档名称 | `<skill-name>` 功能测试与验收记录（企业版） |
| 文档编号 | `<doc-id>` |
| 文档版本 | `v1.0` |
| 编制人 | `<author>` |
| 评审人 | `<reviewer-or-pending>` |
| 批准人 | `<approver-or-pending>` |
| 编制日期 | `<date>` |
| 最后更新日期 | `<date>` |

## 2. 基本信息

| 项目 | 内容 |
|---|---|
| Skill 名称 | `<skill-name>` |
| Skill 路径 | `<skill-path>` |
| 所属项目/团队 | `<team-or-project>` |
| 需求来源 | `<request-source>` |
| 适用版本 | `<version>` |
| 测试类型 | `<first-acceptance-or-regression>` |
| 发布目标 | `<internal-or-clawhub>` |
| 测试环境 | `<environment-summary>` |
| 工作区 | `<workspace-path>` |

## 3. 测试目标

```text
<goal-summary>
```

> 说明：本报告用于验收与记录，不代表已对目标 skill 或其依赖进行修复。除非用户另行发起修复任务，本次输出仅包含验证结论、证据与建议。

## 4. 规范检查结果

| 检查项 | 结果 | 说明 |
|---|---|---|
| `SKILL.md` 存在 | `<pass-or-fail>` | `<note>` |
| `name` 合规 | `<pass-or-fail>` | `<note>` |
| `description` 存在 | `<pass-or-fail>` | `<note>` |
| `description` 触发导向 | `<pass-or-fail>` | `<note>` |
| `description` 是否符合 `Use when` 风格 | `<pass-or-fail>` | `<note>` |
| 目录结构合理 | `<pass-or-fail>` | `<note>` |
| `agents/openai.yaml` 一致性 | `<pass-or-fail-or-na>` | `<note>` |
| 脚本/引用路径有效 | `<pass-or-fail-or-na>` | `<note>` |

## 5. 最佳实践审计结果

| 检查项 | 结果 | 说明 |
|---|---|---|
| 触发设计清晰 | `<pass-or-fail>` | `<note>` |
| 渐进披露合理 | `<pass-or-fail>` | `<note>` |
| 资源组织清晰 | `<pass-or-fail>` | `<note>` |
| 指令边界明确 | `<pass-or-fail>` | `<note>` |
| 证据标准清晰 | `<pass-or-fail>` | `<note>` |
| 失败项可见 | `<pass-or-fail>` | `<note>` |
| 报告输出稳定 | `<pass-or-fail>` | `<note>` |
| Marketplace 发布适配 | `<pass-or-fail>` | `<note>` |

## 6. 静态检查结果

| 检查项 | 结果 | 说明 |
|---|---|---|
| 说明与目标行为一致 | `<pass-or-fail>` | `<note>` |
| 关键资源存在 | `<pass-or-fail>` | `<note>` |
| 关键限制已写明 | `<pass-or-fail>` | `<note>` |

## 7. 敏感能力审计

| 编号 | 能力类型 | 发现位置 | 与声明用途是否匹配 | 风险级别 | 说明 |
|---|---|---|---|---|---|
| CAP-01 | `<command-exec-or-sensitive-file-or-broad-http-or-destructive-op>` | `<file-or-script-ref>` | `<yes-partial-no>` | `<low-medium-high>` | `<note>` |

> 审计提示：
>
> - “无恶意行为” 不等于 “低风险”。
> - 需要单独写明命令执行、本地敏感文件访问、宽范围 HTTP 调用、批量删除/取消/结束等高权限能力。
> - 如果实际能力明显大于 skill 对外声明，应在结论中降级处理。

## 8. 加载检查

| 检查项 | 结果 | 说明 |
|---|---|---|
| `openclaw gateway restart` | `<pass-or-fail>` | `<note>` |
| `openclaw skills list` 可见 | `<pass-or-fail>` | `<note>` |
| `openclaw skills info` 路径正确 | `<pass-or-fail>` | `<note>` |

## 9. 功能清单

| Feature ID | 功能名称 | 类型 | 来源证据 | 动态验证要求 | 备注 |
|---|---|---|---|---|---|
| F-01 | `<feature-name>` | `<core-operation-or-guardrail-or-output-rule>` | `<skill-line-or-script-ref>` | `<required-optional-blocked>` | `<note>` |

## 10. 覆盖矩阵

| Feature ID | 关联用例 | 覆盖方式 | 当前状态 | 说明 |
|---|---|---|---|---|
| F-01 | `<TC-01, TC-05>` | `<dynamic-or-static-only-or-pending-or-out-of-scope>` | `<covered-or-static-only-or-pending-or-blocked-or-out-of-scope>` | `<note>` |

> 判定规则：
>
> - `covered`：必须有真实动态执行证据，不得仅凭代码阅读或链路推断给出。
> - `static-only`：仅有静态/规范/脚本层证据，不能等同于动态覆盖。
> - `pending`：本轮计划验证但未执行完成，或缺前置条件。
> - `blocked`：本轮因环境、账号、依赖或平台问题无法验证。
> - `out-of-scope`：明确不在本轮范围内，且该收缩范围已记录。

## 11. 动态用例结果

| Case ID | 类型 | 输入摘要 | 预期 | 实际 | 结论 | 证据 |
|---|---|---|---|---|---|---|
| TC-01 | Positive | `<prompt-summary>` | `<expected>` | `<actual>` | `<pass-fail-pending>` | `<run-id-or-note>` |
| TC-02 | Negative | `<prompt-summary>` | `<expected>` | `<actual>` | `<pass-fail-pending>` | `<run-id-or-note>` |
| TC-03 | Incomplete Input | `<prompt-summary>` | `<expected>` | `<actual>` | `<pass-fail-pending>` | `<run-id-or-note>` |
| TC-04 | Safety | `<prompt-summary>` | `<expected>` | `<actual>` | `<pass-fail-pending>` | `<run-id-or-note>` |

## 12. 功能覆盖结论

| 项目 | 内容 |
|---|---|
| 声明功能总数 | `<feature-count>` |
| 已动态覆盖 | `<dynamic-covered-count>` |
| 仅静态覆盖 | `<static-only-count>` |
| 待补验证 | `<pending-count>` |
| 环境阻塞 | `<blocked-count>` |
| 超出本轮范围 | `<out-of-scope-count>` |

```text
<coverage-summary>
```

## 13. 环境问题

| 编号 | 问题 | 影响 | 处理建议 |
|---|---|---|---|
| ENV-01 | `<environment-issue-or-none>` | `<impact>` | `<action>` |

## 14. 缺陷与风险

| 编号 | 类型 | 描述 | 严重级别 | 建议 |
|---|---|---|---|---|
| FINDING-01 | `<spec-or-runtime>` | `<description>` | `<severity>` | `<recommendation>` |

## 15. 验收结论

### 15.1 业务能力结论

- [ ] 通过
- [ ] 有条件通过
- [ ] 不通过

```text
<business-conclusion-summary>
```

### 15.2 平台集成结论

- [ ] 通过
- [ ] 有条件通过
- [ ] 不通过

```text
<integration-conclusion-summary>
```

### 15.3 综合结论说明

```text
<final-conclusion-summary>
```

## 16. 发布建议

> 发布门禁提示：
>
> - 如果存在高风险敏感能力，但用途披露不足或能力边界过宽，不应给出无条件 `通过`。
> - 如果风险可接受但仍需使用者显式知情，优先给出 `有条件通过` 并附带使用建议。

- [ ] 适合内部发布
- [ ] 适合发布到 ClawHub
- [ ] 修复后再发布

```text
<release-recommendation-summary>
```

## 17. 后续动作

- [ ] `<next-action-1>`
- [ ] `<next-action-2>`
- [ ] `<next-action-3>`

## 18. 附件与证据

- [ ] `<artifact-1>`
- [ ] `<artifact-2>`
- [ ] `<artifact-3>`
