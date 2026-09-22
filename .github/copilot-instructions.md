# 任务管理应用 - Copilot 自定义指令

## 项目概述

这是一个 Vue 3 + TypeScript + Vite 构建的任务管理 Web 应用。

**功能特性：**
- ✅ 添加新任务
- ✅ 删除已完成或不需要的任务
- ✅ 将任务标记为已完成
- ✅ 实时任务统计（已完成/总计）

## 开发指南

### 项目结构
```
src/
├── components/
│   └── TaskManager.vue      # 主任务管理组件
├── App.vue                  # 应用根组件
├── style.css               # 全局样式
└── main.ts                 # 入口文件
```

### 技术栈
- **框架**: Vue 3
- **语言**: TypeScript
- **构建工具**: Vite
- **样式**: CSS + Tailwind CSS

### 常见任务

#### 启动开发服务器
```bash
npm run dev
```

#### 构建生产版本
```bash
npm run build
```

#### 预览生产构建
```bash
npm run preview
```

## Copilot 使用

### 自定义代理

- **@TaskUIDesigner**: 用于设计和改进任务管理器 UI/UX
- **@TaskLogic**: 用于实现和调试任务管理逻辑

### 自定义指令

使用以下指令在处理任务相关工作时获得针对性帮助：
- 编写组件代码时遵循 Vue 3 Composition API 最佳实践
- 确保类型安全和使用 TypeScript
- 保持代码的可维护性和可读性

## 部署

应用可通过以下方式部署：
- Vercel (推荐)
- Netlify
- GitHub Pages
- 任何支持静态文件的 Web 服务器

---

**最后更新**: 2026-04-10
