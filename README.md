# 🎬 Galgame 可视化制作工坊

> 无需编程，就能在网页上创作属于你的恋爱冒险游戏（Galgame / 视觉小说）。

把剧情变成一张看得见、拖得动的流程图：创建场景、连接分支、设置选项、埋下数值（Flag），再为每个角色设计专属路线与多结局。内置播放器支持快进、后退、历史记录、自动播放与本地存档/读档；特有的「演示模式」让你直接在游戏画面中拖动角色立绘、替换背景，并自由调整文本框、角色名牌、选项区等 UI 的样式与位置。项目可导出为 JSON 文件，便于备份、分享与二次编辑。

🌐 **在线使用**：https://galgame-studio.onrender.com  
📦 **源码仓库**：https://github.com/alynlox-ui/galgame-studio

**核心特性：**
- 🗺 可视化节点编辑：场景 / 分支 / 结局一目了然，支持拖拽与自动布局
- 🔀 分支与结局判定：选项分支 + 条件自动分支（Flag 数值系统）
- ▶ 内置播放器：快进（已读/全部）、后退、历史、自动、12 个本地存档位
- 🎭 演示模式：在游戏界面中直接点选/拖动背景、角色立绘与 UI 组件并实时调整样式
- 💾 导入 / 导出 JSON：一键备份与迁移
- 🤖 AI 辅助：可配置你自己的 OpenAI 兼容 API（Base URL + Key + 模型），支持 AI 生图（背景 / 人物立绘 / 动作图）与 AI 文本生成，API Key 仅保存在浏览器本地
- ☁ 零依赖单文件实现：可本地打开，也可一键部署到 Render

## 本地运行
1. 安装 Node.js 16+
2. 在项目目录执行：
   ```
   npm start
   ```
3. 浏览器打开 http://localhost:10000

## 部署到 Render

### 方法一：Blueprint 一键部署
1. 把整个文件夹上传到 GitHub 仓库
2. 打开 https://render.com ，注册/登录
3. 点击 **New +** → **Blueprint**
4. 连接你的 GitHub 仓库，Render 会自动读取 `render.yaml` 并创建 Web Service
5. 等待部署完成，即可获得 `https://xxxx.onrender.com` 网页地址

### 方法二：手动创建 Web Service
1. 把整个文件夹上传到 GitHub 仓库
2. Render 控制台：**New +** → **Web Service**
3. 连接仓库，Render 通常会自动识别 Node.js
4. 如果没有自动识别，手动填写：
   - Runtime / Environment: **Node**
   - Build Command: `npm install`
   - Start Command: `node server.js`
   - Instance Type: **Free**
5. 点击 **Deploy Web Service**

### 方法三：静态网站（Static Site）
1. 把 `index.html` 单独上传到 GitHub 仓库
2. Render 控制台：**New +** → **Static Site**
3. 连接仓库，发布目录填 `.`（根目录）
4. 部署即可

> 注意：Render Free Web Service 在无访问一段时间后会休眠，首次打开可能需要 30-60 秒冷启动（页面会先白屏或转圈，稍后刷新即可）。本项目为纯静态单页应用，若希望免休眠，建议使用 Render 的 Static Site 方式部署（方法三）。数据保存在浏览器 localStorage 中。
