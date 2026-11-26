# 香水推荐网站

## 本地运行
1. 安装 Node.js 18 或更高版本
2. `npm install`
3. 复制 `.env.example` 为 `.env`，填入你的 `ANTHROPIC_API_KEY`（在 console.anthropic.com 获取）
4. `npm start`，打开 http://localhost:3000

## 部署
- Render / Railway / Fly.io：连接 Git 仓库，启动命令 `npm start`，在平台后台设置环境变量 `ANTHROPIC_API_KEY`。
- 自己的服务器：`npm start` 配合 pm2，再用 Nginx 反向代理到 3000 端口并配置 HTTPS。

## 注意
- API Key 只放在服务器环境变量里，绝不要写进前端代码或提交到 Git（把 `.env` 加入 `.gitignore`）。
- `server.js` 已做输入校验和限流（每个 IP 每分钟 5 次），上线后可按需调整。
