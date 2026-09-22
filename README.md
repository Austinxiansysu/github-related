# 📝 任务管理 Web 应用

一个使用 Vue 3 + TypeScript + Vite 构建的现代化任务管理 Web 应用，提供直观的用户界面和强大的功能。

## ✨ 功能特性

- ✅ **添加任务**：快速输入并添加新任务
- ✅ **标记完成**：轻松标记任务为已完成或未完成
- ✅ **删除任务**：删除不需要的任务
- ✅ **实时统计**：显示已完成和总任务数
- ✅ **进度追踪**：可视化完成进度条
- ✅ **数据持久化**：使用 LocalStorage 保存任务
- ✅ **响应式设计**：完美适配各种设备
- ✅ **现代界面**：美观的渐变背景和交互效果

## 🚀 快速开始

### 前置条件

- Node.js 16+ 
- npm 或 yarn

### 安装

```bash
# 克隆或打开项目
cd "GitHub related"

# 安装依赖
npm install
```

### 开发

```bash
# 启动开发服务器
npm run dev
```

应用将在 `http://localhost:5173` 上运行，支持热模块替换 (HMR)。

### 生产构建

```bash
# 构建生产版本
npm run build

# 本地预览生产构建
npm run preview
```

## 📁 项目结构

```
project/
├── .github/
│   ├── copilot-instructions.md      # 主要 Copilot 指令
│   ├── AGENTS.md                    # 自定义代理说明
│   └── agents/
│       ├── task-ui-designer.agent.md   # UI/UX 设计代理
│       └── task-logic.agent.md         # 业务逻辑代理
├── src/
│   ├── components/
│   │   ├── TaskManager.vue          # 主任务管理组件
│   │   └── HelloWorld.vue           # 原始示例（可删除）
│   ├── App.vue                      # 应用根组件
│   ├── main.ts                      # 应用入口
│   └── style.css                    # 全局样式
├── package.json                     # 项目配置
├── tsconfig.json                    # TypeScript 配置
├── vite.config.ts                   # Vite 配置
└── README.md                        # 本文件
```

## 🛠 技术栈

| 技术 | 版本 | 说明 |
|------|------|------|
| **Vue** | 3 | 渐进式 JavaScript 框架 |
| **TypeScript** | 最新 | 为 JavaScript 添加类型安全 |
| **Vite** | 最新 | 下一代前端构建工具 |
| **CSS** | 原生 | 现代 CSS 特性 |

## 📖 使用指南

### 添加任务

1. 在输入框中输入任务标题
2. 按 Enter 键或点击"添加"按钮
3. 任务将立即出现在列表中

### 标记任务完成

1. 点击任务左侧的复选框
2. 已完成的任务会显示删除线
3. 统计数字会实时更新

### 删除任务

1. 点击任务右侧的 🗑️ 按钮
2. 任务将从列表中删除
3. 统计数字会实时更新

## 🔧 Copilot 自定义代理

本项目包含两个专门的 Copilot 代理，可帮助改进应用：

### TaskUIDesigner (@TaskUIDesigner)
用于设计和改进用户界面

### TaskLogic (@TaskLogic)
用于实现和调试业务逻辑

详见 [.github/AGENTS.md](.github/AGENTS.md)

## 🎨 UI 特性

- **渐变背景**：紫色渐变主题
- **玻璃态效果**：现代化的模糊透明背景
- **响应式网格**：自适应各种屏幕尺寸
- **平滑动画**：悬停和交互效果
- **无障碍设计**：完整的 ARIA 标签支持

## 💾 数据持久化

任务使用浏览器的 LocalStorage 保存，自动保存每次修改。

## 🚀 部署

### Vercel 部署 (推荐)

1. 将项目推送到 GitHub
2. 在 Vercel 中导入项目
3. 自动检测 Vite 配置并部署

### Netlify 部署

```bash
npm install -g netlify-cli
netlify deploy --prod --dir=dist
```

## 📚 学习资源

- [Vue 3 官方文档](https://vuejs.org/)
- [TypeScript 文档](https://www.typescriptlang.org/)
- [Vite 文档](https://vitejs.dev/)

## 📄 许可证

MIT License

---

**最后更新**：2026年4月10日  
**版本**：1.0.0
