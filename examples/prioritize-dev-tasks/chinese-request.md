# Chinese Request Example

## Scenario

Validate that the English-distributed Skill follows the user's language.

## Prompt

```text
请使用 $prioritize-dev-tasks 帮我给下面的上线前任务排优先级，并指出能延期的事项。

项目阶段：上线前测试
版本目标：本周五按期发布

任务：
1. 修复管理员导出接口可越权查看其他客户订单的问题。
2. 修复阻塞测试环境部署的构建脚本错误。
3. 优化个人中心页面按钮圆角。
4. 增加下个季度才会使用的主题皮肤配置。
```

## Expected Signals

- The output is in Chinese.
- The authorization issue and blocked deployment are ranked first.
- The button polish and future theme configuration are suggested for
  deferral, removal, or later planning.
