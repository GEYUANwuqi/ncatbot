# FilterRegistry 插件系统

## 📚 完整文档导航

FilterRegistry 是 NCatBot 的核心插件系统，提供了强大而灵活的消息过滤和命令处理功能。

### 🚀 快速开始
- **[快速开始指南](./FilterRegistry-快速开始.md)** - 5分钟上手 FilterRegistry
- **[完整功能指南](./FilterRegistry-完整指南.md)** - 所有功能的详细说明

### 🎯 深入学习
- **[最佳实践](./FilterRegistry-最佳实践.md)** - 专业开发技巧和模式
- **[实战案例](./FilterRegistry-实战案例.md)** - 真实应用场景和完整代码

### 🧪 质量保证
- **[测试指南](./FilterRegistry-测试指南.md)** - 全面的测试方法和框架
- **[常见问题解答](./FilterRegistry-FAQ.md)** - 问题排查和解决方案

---

## ⚡ 核心特性

### 🎯 装饰器驱动
通过简单的装饰器轻松创建功能丰富的机器人插件：

```python
@filter.command("hello")
async def say_hello(self, event: BaseMessageEvent):
    await event.reply("你好！🤖")

@filter.admin_only()
@filter.command("admin")
async def admin_function(self, event: BaseMessageEvent):
    await event.reply("管理员功能")
```

### 🔒 权限管理
内置 RBAC 权限系统，支持用户、管理员、Root 三级权限：

```python
@filter.admin_only()    # 管理员权限
@filter.root_only()     # Root权限
```

### 📱 消息类型过滤
精确控制命令的响应场景：

```python
@filter.group_message()    # 仅群聊响应
@filter.private_message()  # 仅私聊响应
```

### 🎨 自定义过滤器
强大的自定义过滤逻辑，支持 Lambda 和独立函数：

```python
@filter.custom(lambda event: '紧急' in event.raw_message)
async def emergency_handler(self, event: BaseMessageEvent):
    await event.reply("收到紧急消息！⚠️")
```

### 📝 智能参数解析
自动类型转换和 MessageSegment 支持：

```python
@filter.command("计算")
async def calculate(self, event: BaseMessageEvent, a: int, b: int):
    result = a + b
    await event.reply(f"{a} + {b} = {result}")
```

---

## 🌟 为什么选择 FilterRegistry？

### ✨ 简单易用
- **零学习成本** - 熟悉 Python 装饰器即可上手
- **直观的API** - 函数名和装饰器含义清晰
- **丰富的示例** - 完整的文档和实战案例

### 🚀 功能强大
- **全面的过滤器** - 权限、消息类型、自定义逻辑
- **智能解析** - 参数类型自动转换
- **事件支持** - 消息、通知、请求事件全覆盖

### 🔧 高度灵活
- **装饰器组合** - 多个过滤器自由组合
- **可扩展架构** - 轻松添加自定义功能
- **配置驱动** - 动态调整插件行为

### 📊 生产就绪
- **性能优化** - 高效的事件处理机制
- **错误处理** - 完善的异常处理和日志
- **测试支持** - 内置测试框架

---

## 🏆 成功案例

- **签到系统** - 每日签到、连续奖励、排行榜
- **天气查询** - 实时天气、预报、城市管理
- **群管理** - 违规检测、自动化处理、权限控制
- **积分商城** - 积分获取、商品管理、购买记录

查看 [实战案例](./FilterRegistry-实战案例.md) 了解详细实现。

---

## 📖 推荐学习路径

### 初学者路径
1. 📖 [快速开始](./FilterRegistry-快速开始.md) - 了解基础概念
2. 🎯 创建第一个插件
3. 🧪 [测试指南](./FilterRegistry-测试指南.md) - 确保代码质量

### 进阶开发者路径
1. 📚 [完整功能指南](./FilterRegistry-完整指南.md) - 掌握所有功能
2. 🎨 [最佳实践](./FilterRegistry-最佳实践.md) - 专业开发技巧
3. 💼 [实战案例](./FilterRegistry-实战案例.md) - 真实项目经验

### 问题解决路径
1. 🔍 [常见问题解答](./FilterRegistry-FAQ.md) - 快速找到解决方案
2. 📝 查看日志文件获取详细错误信息
3. 🧪 使用测试框架验证功能

---

## 🤝 社区支持

- **问题反馈** - 遇到问题请查看 [FAQ](./FilterRegistry-FAQ.md)
- **最佳实践** - 分享你的插件开发经验
- **功能建议** - 提出新功能需求

---

## 📄 许可证

本项目遵循开源许可证，欢迎贡献代码和文档改进。

---

*开始你的机器人开发之旅吧！🎉*
