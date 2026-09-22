# GitHub Related (Vue 3 + TS + Vite)

## 项目说明

物流公司 AI 官网搭建项目，基于 Vue 3 + TypeScript + Vite。包含 SYSU 校园工具 Skill 定义。

## 项目结构

- `src/` — Vue 组件源码（App.vue、components/TaskManager.vue、main.ts）
- `public/` — 静态资源
- `SYSU-Anything.skill/` — SYSU 校园工具 Skill 定义
- `.github/` — GitHub Copilot 配置和 agent 定义
- `vite.config.ts` — Vite 构建配置

## Git 提交规范

- 每次改动后执行 `git add . && git commit -m "描述"`
- commit message 用中文
- 不要提交 `node_modules/`、`dist/`（已在 .gitignore 排除）
- 改完推送到远程：`git push`

## 开发命令

- `npm run dev` — 启动开发服务器
- `npm run build` — 构建生产版本

## 禁止事项

- 不要提交 `node_modules/`、`dist/`、`.env` 文件
- 不要修改 `package-lock.json`（由 npm 自动管理）
