# Galgame 可视化制作工坊

一个无需编程的 Galgame 制作工具，单文件网页，支持：
- 可视化节点编辑（场景、分支、结局）
- 播放器：快进 / 后退 / 历史 / 自动 / 存档读档
- 演示模式：在游戏界面直接调整角色立绘、背景、文本框、角色名牌、选项区 UI
- 导入 / 导出 JSON 项目

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

> 注意：Free 实例首次访问可能需要 30-60 秒启动；数据保存在浏览器 localStorage 中。
