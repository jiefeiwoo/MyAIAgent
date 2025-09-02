# AI助手群聊 - API配置说明

## 🎯 概述

这个AI助手群聊网站支持两种模式：
1. **模拟模式**：使用预设的回复内容，无需配置API
2. **真实API模式**：调用真实的AI服务，需要配置API密钥

## 🔑 获取API密钥

### 1. DeepSeek API
- 访问 [DeepSeek官网](https://platform.deepseek.com/)
- 注册账号并登录
- 在控制台中创建API密钥
- 复制API密钥

### 2. 通义千问 API
- 访问 [阿里云通义千问](https://bailian.console.aliyun.com/?tab=model#/api-key)
- 使用阿里云账号登录
- 在API密钥管理中创建密钥
- 复制API密钥

### 3. 豆包 API
- 访问 [豆包官网](https://console.volcengine.com/)
- 注册账号并登录
- 在开发者中心创建API密钥
- 复制API密钥

**注意**: 豆包API使用火山引擎的端点，格式为 `https://ark.cn-beijing.volces.com/api/v3/chat/completions`

**模型名称**: 系统会自动尝试以下模型名称：
- `doubao-pro` (推荐)
- `doubao-turbo`
- `doubao-lite`
- `doubao-pro-8k`
- `doubao-pro-4k`
- `doubao-plus`
- `doubao-standard`

如果某个模型不可用，系统会自动尝试下一个模型。

## ⚙️ 配置步骤

### 步骤1：打开配置页面
双击打开 `index-simple-with-api.html` 文件

### 步骤2：输入API密钥
在页面顶部的"API配置"区域：
- 输入DeepSeek API密钥
- 输入通义千问API密钥  
- 输入豆包API密钥

### 步骤3：选择模式
- 点击"模拟模式"：使用预设回复（推荐新手）
- 点击"真实API模式"：使用真实AI服务

### 步骤4：开始对话
在聊天框中输入问题，AI助手会根据配置的模式回复

## 🔧 技术细节

### API端点
- **DeepSeek**: `https://api.deepseek.com/v1/chat/completions`
- **通义千问**: `https://dashscope.aliyuncs.com/api/v1/services/aigc/text-generation/generation`
- **豆包**: `https://ark.cn-beijing.volces.com/api/v3/chat/completions`

### 请求格式
每个API都有特定的请求格式，代码中已包含示例实现。

### 错误处理
- API密钥未配置：显示"离线"状态
- API调用失败：显示错误信息
- 网络问题：自动重试机制

## 💡 使用建议

### 新手用户
1. 先使用"模拟模式"熟悉界面
2. 了解基本功能后再配置API

### 开发者
1. 获取API密钥后直接配置
2. 根据需要修改API调用逻辑
3. 添加更多错误处理和重试机制

## 🚨 注意事项

### 安全性
- API密钥会保存在浏览器本地存储中
- 不要在不安全的设备上使用
- 定期更换API密钥

### 费用
- 真实API调用会产生费用
- 注意控制使用量
- 监控API使用情况

### 限制
- 每个API都有调用频率限制
- 注意遵守服务条款
- 避免滥用API服务

## 🆘 常见问题

### Q: API密钥输入后没有反应？
A: 检查密钥是否正确，确保网络连接正常

### Q: 为什么有些AI助手显示离线？
A: 在API模式下，只有配置了密钥的AI助手才会显示在线

### Q: 如何切换回模拟模式？
A: 点击"模拟模式"按钮即可

### Q: 配置会保存吗？
A: 是的，配置会保存在浏览器本地存储中

## 🔄 更新日志

- v1.0: 基础功能实现
- v1.1: 添加API配置支持
- v1.2: 改进错误处理和用户体验

## 📞 技术支持

如果遇到问题，请检查：
1. API密钥是否正确
2. 网络连接是否正常
3. 浏览器控制台是否有错误信息

---

**注意**: 这个项目仅供学习和个人使用，请遵守相关API服务的使用条款。 