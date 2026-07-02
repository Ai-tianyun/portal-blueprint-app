# Portal Blueprint App - 开发指南

## 📋 项目信息

这是一个基于 **Nuxt 3 + Vue 3 + Tailwind CSS** 的现代化 Web 应用项目。

**技术栈：**
- Nuxt 3（Vue 3 框架）
- Tailwind CSS（样式框架）
- Pinia（状态管理）
- Headless UI（UI 组件）
- Vitest（单元测试）
- Husky + CommitLint（代码提交规范）

---

## 🚀 快速开始

### 1️⃣ 环境要求

在开始之前，请确保你已安装：
- **Node.js**: v14.16.0 及以上（推荐 v16+ 或 v17+）
- **Yarn**: v3.2.0（包管理器）

**检查版本：**
```bash
node -v
yarn -v
```

### 2️⃣ 在电脑上操作（不是手机！）

#### 方式一：使用 Git 克隆

```bash
# 克隆仓库到本地
git clone https://github.com/Ai-tianyun/portal-blueprint-app.git

# 进入项目目录
cd portal-blueprint-app

# 切换到 release 分支（如果需要）
git checkout release
```

#### 方式二：如果已经克隆了

```bash
# 进入项目目录
cd portal-blueprint-app

# 更新最新代码
git pull origin release
```

### 3️⃣ 安装依赖

```bash
yarn install
```

这会安装所有项目依赖（可能需要几分钟）。

### 4️⃣ 启动开发服务器

```bash
yarn dev
```

你会看到类似的输出：
```
✔ Ready in Xs
➜  Local:   http://localhost:3000
```

### 5️⃣ 访问应用

在浏览器中打开：
```
http://localhost:3000
```

---

## 📚 常用命令

| 命令 | 说明 |
|------|------|
| `yarn install` | 安装所有依赖 |
| `yarn dev` | 启动开发服务器（热更新） |
| `yarn build` | 构建生产版本 |
| `yarn start` | 运行生产构建 |
| `yarn test:unit` | 运行单元测试 |
| `yarn test:coverage` | 运行测试覆盖率分析 |
| `yarn allupdate` | 交互式更新依赖 |

---

## 📁 项目结构

```
portal-blueprint-app/
├── components/          # Vue 组件
├── pages/              # 页面（自动路由）
├── store/              # Pinia 状态管理
├── types/              # TypeScript 类型定义
├── assets/             # 静态资源（图片、字体等）
├── test/               # 测试文件
├── nuxt.config.ts      # Nuxt 配置文件
├── tailwind.config.js  # Tailwind CSS 配置
├── tsconfig.json       # TypeScript 配置
├── package.json        # 项目依赖和脚本
└── yarn.lock          # 依赖锁定文件
```

---

## 🔧 开发工作流

### 创建新页面

在 `pages/` 目录下创建 `.vue` 文件，Nuxt 会自动生成路由。

例如：`pages/about.vue` → 访问 `http://localhost:3000/about`

### 创建新组件

在 `components/` 目录下创建 `.vue` 文件，Nuxt 会自动注册组件。

```vue
<!-- components/MyButton.vue -->
<template>
  <button class="px-4 py-2 bg-blue-500 text-white rounded">
    {{ label }}
  </button>
</template>

<script setup lang="ts">
defineProps({
  label: String
})
</script>
```

### 使用状态管理（Pinia）

```typescript
// store/counter.ts
import { defineStore } from 'pinia'

export const useCounterStore = defineStore('counter', () => {
  const count = ref(0)
  
  const increment = () => count.value++
  
  return { count, increment }
})
```

---

## ✅ 测试

### 运行单元测试

```bash
yarn test:unit
```

### 查看测试覆盖率

```bash
yarn test:coverage
```

---

## 📦 部署

### 构建生产版本

```bash
yarn build
```

### 启动生产服务器

```bash
yarn start
```

### 部署到云平台

可以部署到以下平台：
- **Vercel**（推荐）
- **Netlify**
- **GitHub Pages**
- **传统服务器**

---

## 🐛 常见问题

### 1. 依赖安装失败

```bash
# 清除缓存
rm -rf node_modules yarn.lock

# 重新安装
yarn install
```

### 2. 端口 3000 已被占用

```bash
# 使用其他端口
yarn dev -- --port 3001
```

### 3. 热更新不工作

检查你是否修改了 `nuxt.config.ts`，可能需要重启开发服务器。

---

## 📝 Git 提交规范

项目使用 CommitLint 规范提交消息：

```bash
# 推荐的提交格式
git commit -m "feat: 添加新功能"
git commit -m "fix: 修复 bug"
git commit -m "docs: 更新文档"
git commit -m "style: 代码风格调整"
```

---

## 🔗 相关链接

- [Nuxt 3 文档](https://nuxt.com)
- [Vue 3 文档](https://vuejs.org)
- [Tailwind CSS 文档](https://tailwindcss.com)
- [Pinia 文档](https://pinia.vuejs.org)

---

## ❓ 需要帮助？

如有问题，请：
1. 检查这份文档
2. 查看项目的 README.md
3. 提交 Issue 到 GitHub

祝开发愉快！🎉
