[![Vue](https://img.shields.io/badge/-Vue-4FC08D?style=for-the-badge&logo=Vue.js&logoColor=white)](https://vuejs.org/)
[![TailwindCSS](https://img.shields.io/badge/-TailwindCSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Vite](https://img.shields.io/badge/-Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
# Vue 3  + Vite + Tailwindcss Todo List

该模板提供了一个使用Vue 3和Vite开发的基本Todo List应用程序。它利用了Vue 3的`<script setup>`单文件组件（SFC），使代码更简洁高效。

## 快速开始

要开始使用这个项目，请按照以下步骤操作：

1. 克隆仓库：`git clone https://github.com/laohubb/letsdo.git`
2. 进入项目目录：`cd letsdo`
3. 安装依赖项：`npm install`
4. 启动开发服务器：`npm run dev`
5. 在浏览器中打开：`http://localhost:3000`

## 功能

- 在输入框中输入文本并按Enter键或点击“添加任务”按钮，以添加新的任务。
- 任务可以逐个添加，也可以作为用连字符（-）分隔的列表或以数字加句点（1.、2.等）的方式添加。
- 查看未完成的任务列表，并通过点击“完成”按钮将其标记为已完成。
- 查看已完成的任务列表，并通过点击“取消完成”按钮将其标记为未完成。
- 通过点击“清除已完成任务”按钮，清除所有已完成的任务。

## 项目结构

- `index.html`：主HTML文件，用作应用程序的入口点。
- `main.js`：应用程序的入口点，在此处初始化Vue应用程序。
- `App.vue`：应用程序的根组件，包含Todo List组件。
- `TodoList.vue`：渲染Todo List界面并处理管理任务的逻辑的组件。
- `style.css`：应用程序的全局样式。

## 推荐的IDE设置

为了获得最佳的开发体验，建议在您偏爱的IDE中设置以下工具：

- [Visual Studio Code](https://code.visualstudio.com/)，并安装以下扩展：
    - [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)（如果已安装Vetur，请禁用Vetur）
    - [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin)

这些扩展提供了增强的Vue支持、TypeScript支持以及针对Vue 3和Vite项目的更好工具支持。

## 更多信息

如需了解有关使用Vue 3和Vite开发Vue应用程序的更多信息，请参阅官方文档：

- [Vue 3 文档](https://v3.vuejs.org/)
- [Vite 文档](https://vitejs.dev/)

愿您在使用Vue 3和Vite构建Todo List应用程序时获得愉快的开发体验！
