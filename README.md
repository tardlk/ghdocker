# 🐳 GH Docker 镜像同步工具

本项目通过 GitHub Actions 自动将指定的 Docker 镜像同步到 GitHub Container Registry（GHCR），并在 README 中展示同步状态。  
适用于国内服务器、NAS 等环境，配合加速源使用效果更佳。

---

## 🚀 功能特点

- 自动拉取源镜像并同步到 GHCR
- 仅在镜像有更新时才同步，节省流量
- 支持从 README 表格读取镜像列表，无需额外配置文件
- 自动更新同步状态表格（含拉取命令、更新时间、备注）
- 保留你手动填写的说明内容，不会被覆盖
- 拉取失败自动标记 ❌，便于排查

---

## 📦 镜像同步状态  
<!--SYNC-TABLE-START-->
## 📦 镜像同步状态
最后更新时间（北京时间）：尚未同步

| 源镜像 | 同步后镜像（可复制） | 更新时间（北京时间） | 备注 |
| ------ | ------------------- | -------------------- | ---- |
| `nginx:latest` | `docker pull ghcr.io/YOUR_USERNAME/nginx:latest` | 尚未同步 | 推荐使用加速源：ghcr.nju.edu.cn |
| `louislam/dockge:1` | `docker pull ghcr.io/YOUR_USERNAME/louislam/dockge:1` | 尚未同步 | Dockge 面板 |
| `redis:7` | `docker pull ghcr.io/YOUR_USERNAME/redis:7` | 尚未同步 | Redis 7 稳定版 |
<!--SYNC-TABLE-END-->

> 请将 `YOUR_USERNAME` 替换为你的 GitHub 用户名。工作流运行后会自动更新同步后镜像和时间。

---

## ✏️ 如何添加新镜像

只需在上方表格中添加一行，填写源镜像（必须带标签），同步后镜像和备注列可以先填占位，工作流会自动更新。

示例：
```markdown
| `bitnami/mariadb:11.4.2` | `docker pull ghcr.io/YOUR_USERNAME/bitnami/mariadb:11.4.2` | 尚未同步 | Bitnami 版 MariaDB |
