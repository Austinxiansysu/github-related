# 🎯 任务管理应用 - Copilot 自定义指令使用指南

## 项目设置完成 ✅

您的任务管理 Web 应用已成功创建！以下是所有已配置的自定义 Copilot 功能。

## 📋 已完成的功能

### ✨ 应用功能
- [x] 添加任务
- [x] 删除任务  
- [x] 标记任务完成/未完成
- [x] 实时任务统计
- [x] 进度条显示
- [x] LocalStorage 数据持久化
- [x] 响应式设计
- [x] 现代化 UI 设计

### 📁 项目结构
- [x] Vue 3 + TypeScript + Vite 脚手架
- [x] TaskManager.vue 主组件
- [x] 全局样式配置
- [x] .github 目录结构

### 🛠 Copilot 自定义配置
- [x] copilot-instructions.md - 工作区级指令
- [x] AGENTS.md - 代理说明文档
- [x] task-ui-designer.agent.md - UI 设计代理
- [x] task-logic.agent.md - 业务逻辑代理

### 📚 文档
- [x] README.md - 完整项目文档
- [x] 本使用指南

## 🚀 快速启动

### 1. 开发模式

应用已在运行于：**http://localhost:5173**

在 VS Code 中打开浏览器预览或访问上述链接查看实时应用。

### 2. 停止服务器

在终端按 `q` 然后按 Enter 停止开发服务器。

### 3. 构建生产版本

```bash
npm run build
```

## 🤖 使用 Copilot 代理

### TaskUIDesigner 代理 (@TaskUIDesigner)

**用途**：改进用户界面和用户体验

**使用场景**：
- 改进任务列表样式
- 优化响应式布局
- 添加动画效果
- 改进无障碍特性
- 美化输入框和按钮

**示例提示词**：
```
@TaskUIDesigner 给任务项添加更多的视觉反馈，比如悬停效果和动画过渡
```

```
@TaskUIDesigner 优化手机屏幕上的布局，使触摸目标更大
```

```
@TaskUIDesigner 添加深色模式支持
```

### TaskLogic 代理 (@TaskLogic)

**用途**：实现和改进应用业务逻辑

**使用场景**：
- 添加任务分类功能
- 实现任务搜索
- 添加任务优先级
- 实现撤销功能
- 优化性能
- 添加新的数据操作

**示例提示词**：
```
@TaskLogic 添加任务分类功能，使用户可以将任务分组
```

```
@TaskLogic 实现任务搜索和过滤功能
```

```
@TaskLogic 添加任务编辑功能，允许用户修改已有任务
```

## 📂 自定义指令文件位置

所有 Copilot 自定义文件都位于 `.github` 目录：

```
.github/
├── copilot-instructions.md          # 主工作区指令
├── AGENTS.md                        # 代理文档
└── agents/
    ├── task-ui-designer.agent.md    # UI 设计代理
    └── task-logic.agent.md          # 逻辑开发代理
```

## 💡 工作流示例

### 场景 1：改进 UI

1. 在 Copilot Chat 中使用：
   ```
   @TaskUIDesigner 改进任务输入框的设计，使其更引人注目
   ```

2. Copilot 会提供 CSS 改进建议或代码片段

3. 应用所建议的更改到 `src/components/TaskManager.vue`

4. 在浏览器中实时查看效果（HMR）

### 场景 2：添加新功能

1. 在 Copilot Chat 中使用：
   ```
   @TaskLogic 添加任务的创建时间显示，并按时间排序
   ```

2. Copilot 会提供实现建议和代码

3. 更新 `src/components/TaskManager.vue`

4. 测试新功能

## 🔧 修改自定义配置

### 编辑工作区指令

编辑 `.github/copilot-instructions.md` 文件来添加或修改工作区级别的指令。

### 编辑代理定义

编辑 `.github/agents/` 目录下的 `.agent.md` 文件来修改代理的行为和描述。

### 添加新代理

在 `.github/agents/` 目录创建新的 `*.agent.md` 文件，包含 YAML 前置和代理说明。

## 📖 参考资源

- [VS Code Copilot 自定义文档](https://code.visualstudio.com/docs/copilot/copilot-customization)
- [Vue 3 文档](https://vuejs.org/)
- [TypeScript 文档](https://www.typescriptlang.org/)
- [Vite 文档](https://vitejs.dev/)

## 🎨 已实现的设计特性

- ✅ 紫色渐变背景
- ✅ 玻璃态效果
- ✅ 响应式网格布局
- ✅ 平滑过渡和动画
- ✅ 完整的 ARIA 标签
- ✅ 暗色模式支持（通过系统偏好）

## 📊 文件清单

```
✅ .github/copilot-instructions.md      (主指令)
✅ .github/AGENTS.md                    (代理说明)
✅ .github/agents/task-ui-designer.agent.md
✅ .github/agents/task-logic.agent.md
✅ src/components/TaskManager.vue       (主组件)
✅ src/App.vue                          (根组件)
✅ src/style.css                        (全局样式)
✅ src/main.ts                          (入口文件)
✅ README.md                            (项目文档)
✅ package.json                         (依赖配置)
✅ vite.config.ts                       (Vite 配置)
✅ tsconfig.json                        (TypeScript 配置)
```

## 🎯 后续步骤

### 推荐操作

1. **测试应用**
   - 在 http://localhost:5173 上测试各项功能
   - 在不同设备上测试响应式设计

2. **使用 Copilot 代理**
   - 尝试 @TaskUIDesigner 改进界面
   - 尝试 @TaskLogic 添加新功能

3. **部署应用**
   - 推送到 GitHub
   - 使用 Vercel 或 Netlify 部署

4. **持续改进**
   - 根据需要修改自定义指令
   - 添加新的代理定义

## ❓ 常见问题

**Q: 如何创建更多自定义代理？**
A: 在 `.github/agents/` 目录创建新的 `*.agent.md` 文件，遵循现有代理的格式。

**Q: 自定义指令不生效？**
A: 
- 检查文件是否在正确的 `.github/` 目录
- 确保 YAML 前置正确（`---` 分隔符）
- 重启 VS Code

**Q: 如何在不同的工作空间使用这些配置？**
A: 所有文件都在项目中，打开项目后自动生效。

**Q: 可以个性化样式吗？**
A: 完全可以！编辑 `src/components/TaskManager.vue` 中的样式部分。

## 🆘 支持

如遇到问题，请：

1. 检查 browser console 是否有错误
2. 查看 VS Code 的 Copilot 输出面板
3. 查阅 [VS Code 文档](https://code.visualstudio.com/docs)

---

**祝您使用愉快！** 🎉

如有任何问题，请随时使用 Copilot Chat 提问。

*最后更新：2026-04-10*
