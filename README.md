# SemVer Versioning Skill

按 [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html) 管理应用开发过程中的版本号。该技能帮助 AI 根据公开 API、向后兼容性和变更类型判断 `Major.Minor.Patch`，并在开发过程中同步更新项目版本配置。

## 主要能力

- 判断 Major、Minor、Patch 版本升级级别
- 正确处理多位数字版本，例如 `2.6.9 → 2.6.10` 和 `2.6.65`
- 识别公开 API、配置、协议、数据格式和用户流程的破坏性变化
- 管理 `0.y.z` 初始开发阶段
- 判断何时建议进入 `1.0.0` 正式版本，并要求用户确认
- 处理 `alpha`、`beta`、`rc` 预发布版本和构建元数据
- 在每次开发时读取、更新并报告项目版本配置

## 版本规则

```text
破坏性、不向后兼容的变更       → Major，X+1，Y/Z 归零
向后兼容的新功能               → Minor，Y+1，Z 归零
向后兼容的 Bug 修复             → Patch，Z+1
```

版本号始终保持三段格式 `X.Y.Z`，但每段都是可持续增长的非负整数。Patch 版本不会因为达到 `9` 就自动升级 Minor：

```text
2.6.9  → 2.6.10  # Patch 修复
2.6.65 → 2.7.0   # 向后兼容的新功能
2.6.65 → 3.0.0   # 破坏性变更
```

## 使用方式

将 [`SKILL.md`](./SKILL.md) 添加到支持 Manus Skills 的环境中，或将其内容作为 AI 的版本管理规则。在应用开发、修复 Bug、新增功能和准备发布时，让 AI 按技能中的流程读取当前版本、分析变更、更新版本配置并报告升级原因。

从 `0.y.z` 进入 `1.0.0` 不由版本号、功能数量或开发时间自动触发。只有公开 API 稳定、核心功能可用、准备承诺兼容性并获得用户或项目负责人的确认后，才升级到 `1.0.0`。

## 版本历史

| 版本 | 说明 |
|---|---|
| [`v0.1.0`](https://github.com/ZYJ882/semver-versioning/releases/tag/v0.1.0) | 初始 SemVer 版本判断技能，覆盖 Major、Minor、Patch、公开 API、预发布版本和 `0.y.z`。 |
| [`v0.2.0`](https://github.com/ZYJ882/semver-versioning/releases/tag/v0.2.0) | 增加持续开发过程中的版本管理流程、`0.y.z → 1.0.0` 正式发布条件和用户确认机制。 |

## 官方参考

- [SemVer 2.0.0 官方规范](https://semver.org/spec/v2.0.0.html)
- [npm 官方 SemVer 说明](https://docs.npmjs.com/about-semantic-versioning/)
