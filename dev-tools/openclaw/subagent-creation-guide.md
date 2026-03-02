# OpenClaw 子 Agent 创建方案指南

## 1. 子 Agent 概念与用途

### 1.1 什么是子 Agent
子 Agent（Sub-agent）是 OpenClaw 中的一种并行任务执行机制，它允许主会话创建独立的、隔离的子会话来处理特定任务。每个子 Agent 拥有自己独立的上下文、内存空间和工具调用权限。

### 1.2 主要用途
- **长时间运行任务**：避免阻塞主会话，如数据收集、文件处理、网络请求等
- **并行处理**：同时执行多个独立任务，提高效率
- **任务隔离**：将复杂任务分解为多个子任务，降低主会话的复杂度
- **错误隔离**：子 Agent 的失败不会影响主会话的正常运行
- **资源管理**：为不同任务分配不同的资源配置和超时策略

### 1.3 子 Agent 与主 Agent 的关系
- **父子关系**：子 Agent 由主 Agent 创建，完成后自动向主 Agent 汇报结果
- **上下文隔离**：子 Agent 无法直接访问主 Agent 的上下文和内存
- **通信机制**：通过完成消息或显式的消息传递进行通信
- **生命周期**：子 Agent 完成任务后可选择自动清理或保留以供后续查询

## 2. 创建子 Agent 的方法

### 2.1 使用 sessions_spawn 工具
OpenClaw 提供了 `sessions_spawn` 工具来创建子 Agent，这是官方推荐的方式。

#### 基本语法
```javascript
sessions_spawn({
  task: "具体的任务描述",
  label: "可选的标签名称",
  timeoutSeconds: 300, // 可选的超时时间（秒）
  cleanup: "delete" // 完成后处理方式："delete" 或 "keep"
})
```

#### 参数详解
| 参数 | 类型 | 必需 | 默认值 | 说明 |
|------|------|------|--------|------|
| `task` | string | 是 | - | 子 Agent 需要执行的具体任务描述 |
| `label` | string | 否 | 自动生成 | 子 Agent 的标识标签，用于后续引用 |
| `timeoutSeconds` | number | 否 | 300 (5分钟) | 任务超时时间，超过此时间将被强制终止 |
| `cleanup` | string | 否 | "delete" | 任务完成后的清理策略："delete"（删除）或 "keep"（保留） |
| `agentId` | string | 否 | "main" | 指定使用的 Agent ID（如果有多 Agent 配置） |

### 2.2 工具调用示例
```javascript
// 简单任务
sessions_spawn({
  task: "收集关于量子计算的最新研究论文",
  label: "quantum-research"
})

// 带超时和清理配置的复杂任务
sessions_spawn({
  task: "分析大型数据集并生成可视化报告",
  label: "data-analysis",
  timeoutSeconds: 1800, // 30分钟超时
  cleanup: "keep" // 保留结果以供后续查询
})
```

## 3. 配置参数详细说明

### 3.1 Task 参数
- **内容要求**：必须清晰、具体地描述任务目标
- **上下文传递**：可以包含必要的上下文信息，但要注意 token 限制
- **指令格式**：建议使用明确的指令格式，如"请完成以下任务：..."

### 3.2 Label 参数
- **命名规范**：建议使用小写字母、数字和连字符
- **唯一性**：同一会话中的 label 应该唯一
- **用途**：用于日志追踪、结果查询和调试

### 3.3 Timeout 参数
- **默认值**：300 秒（5分钟）
- **最大值**：通常受系统配置限制
- **最佳实践**：根据任务复杂度合理设置，避免过长的等待时间

### 3.4 Cleanup 参数
- **delete**：任务完成后自动删除子会话（节省资源）
- **keep**：保留子会话（便于调试和结果查询）

## 4. 使用场景和最佳实践

### 4.1 典型使用场景

#### 场景1：数据收集和整理
```javascript
sessions_spawn({
  task: "系统地整理量子密码算法相关资料，生成一份内容翔实的报告",
  label: "quantum-crypto-report",
  timeoutSeconds: 600
})
```

#### 场景2：文件处理
```javascript
sessions_spawn({
  task: "处理大量图像文件，进行格式转换和压缩",
  label: "image-processing",
  timeoutSeconds: 1200
})
```

#### 场景3：并行 API 调用
```javascript
// 创建多个子 Agent 并行处理
sessions_spawn({ task: "获取用户A的数据", label: "user-a-data" })
sessions_spawn({ task: "获取用户B的数据", label: "user-b-data" })
sessions_spawn({ task: "获取用户C的数据", label: "user-c-data" })
```

### 4.2 最佳实践

#### 任务分解原则
- **单一职责**：每个子 Agent 只负责一个明确的任务
- **适当粒度**：任务既不能太细（增加开销），也不能太粗（失去并行优势）
- **独立性**：尽量减少子 Agent 之间的依赖关系

#### 资源管理
- **合理设置超时**：避免长时间占用系统资源
- **及时清理**：对于不需要保留结果的任务，使用 `cleanup: "delete"`
- **监控资源使用**：注意系统的并发限制和资源消耗

#### 错误处理
- **预期失败**：对于可能失败的任务，考虑重试机制
- **优雅降级**：设计备用方案，当子 Agent 失败时不影响整体流程
- **日志记录**：记录关键操作的日志，便于调试和监控

## 5. 常见问题和解决方案

### 5.1 网关权限问题
**问题描述**：
```
gateway closed (1008): unauthorized: gateway token mismatch
```

**解决方案**：
1. 检查 `~/.openclaw/openclaw.json` 配置文件
2. 确保 `gateway.remote.token` 和 `gateway.auth.token` 的值匹配
3. 如果没有配置，可以添加以下配置：
```json
{
  "gateway": {
    "auth": {
      "token": "your-secret-token"
    },
    "remote": {
      "token": "your-secret-token"
    }
  }
}
```
4. 重启 OpenClaw 服务使配置生效

### 5.2 子 Agent 无法启动
**可能原因**：
- 系统资源不足
- 并发限制达到上限
- 任务描述不清晰

**解决方案**：
- 检查系统资源使用情况
- 减少并发子 Agent 数量
- 优化任务描述，使其更加具体和明确

### 5.3 超时问题
**问题描述**：子 Agent 在完成任务前被强制终止

**解决方案**：
- 根据任务复杂度合理设置 `timeoutSeconds`
- 对于特别复杂的任务，考虑进一步分解为多个子任务
- 监控任务执行时间，逐步优化超时设置

### 5.4 结果丢失
**问题描述**：子 Agent 完成后结果无法获取

**解决方案**：
- 使用 `cleanup: "keep"` 保留子会话
- 主动查询子 Agent 的结果
- 实现结果持久化机制（如保存到文件）

## 6. 代码示例

### 6.1 基础示例
```javascript
// 创建一个简单的子 Agent
const subAgent = await sessions_spawn({
  task: "计算斐波那契数列的前20项",
  label: "fibonacci-calc"
});
```

### 6.2 复杂任务示例
```javascript
// 数据分析任务
await sessions_spawn({
  task: `
    1. 读取 data/sales.csv 文件
    2. 分析月度销售趋势
    3. 识别 top 5 产品
    4. 生成包含图表的 Markdown 报告
    5. 保存报告到 reports/monthly-analysis.md
  `,
  label: "sales-analysis",
  timeoutSeconds: 900,
  cleanup: "keep"
});
```

### 6.3 并行处理示例
```javascript
// 并行处理多个用户的数据
const userTasks = ['Alice', 'Bob', 'Charlie'].map(user => 
  sessions_spawn({
    task: `处理用户 ${user} 的数据并生成个人报告`,
    label: `user-${user.toLowerCase()}-report`,
    timeoutSeconds: 600
  })
);

// 等待所有任务完成
await Promise.all(userTasks);
```

### 6.4 错误处理示例
```javascript
try {
  await sessions_spawn({
    task: "执行可能失败的网络请求",
    label: "network-request",
    timeoutSeconds: 300
  });
} catch (error) {
  console.log("子 Agent 执行失败:", error);
  // 实现备用方案
  await sessions_spawn({
    task: "使用缓存数据生成报告",
    label: "fallback-report"
  });
}
```

## 7. 高级功能

### 7.1 子 Agent 间通信
虽然子 Agent 默认是隔离的，但可以通过以下方式实现通信：
- **共享文件系统**：通过读写文件交换数据
- **消息传递**：使用 `sessions_send` 工具发送消息
- **数据库/存储**：使用外部存储系统

### 7.2 动态任务调整
子 Agent 可以在执行过程中根据实际情况调整任务：
```javascript
// 子 Agent 内部可以根据条件调整后续步骤
if (condition) {
  // 执行路径A
} else {
  // 执行路径B
}
```

### 7.3 监控和调试
- **日志查看**：使用 `sessions_history` 查看子 Agent 的执行历史
- **状态查询**：使用 `sessions_list` 查看活跃的子 Agent
- **性能监控**：记录执行时间和资源使用情况

## 8. 总结

OpenClaw 的子 Agent 功能为复杂任务处理提供了强大的并行和隔离能力。通过合理使用 `sessions_spawn` 工具，可以显著提高任务处理效率和系统可靠性。关键是要遵循最佳实践，合理设计任务分解，正确配置参数，并做好错误处理和资源管理。

在实际使用中，建议从小规模开始，逐步掌握子 Agent 的特性和限制，然后应用到更复杂的场景中。