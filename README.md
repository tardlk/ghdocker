# 🐳 Docker 镜像同步到 GHCR

本仓库使用 GitHub Actions 自动将常用的 Docker 镜像同步到 [GitHub Container Registry (GHCR)](https://ghcr.io)，方便国内外环境快速拉取。

## ✨ 功能
- 每天定时同步一次（北京时间 10:00）
- 支持手动触发同步
- 自动检测镜像是否更新，避免重复推送
- 自动更新下方同步状态表
---

## 📋 镜像同步状态

---

## ⚙️ 工作流说明
- 工作流文件：`.github/workflows/docker-sync.yml`
- 触发方式：
  - 定时任务（每天 UTC 2:00 / 北京时间 10:00）
  - 手动触发
- 同步逻辑：
  1. 从 README 中提取源镜像列表
  2. 拉取源镜像并比对 digest
  3. 如果有更新则推送到 GHCR
  4. 更新 README 中的同步状态表
<!--SYNC-TABLE-START-->
## 📦 镜像同步状态
最后更新时间（北京时间）：2025-09-20 13:51:45

| 源镜像 | 同步后镜像（可复制） | 更新时间（北京时间） | 备注 |
| ------ | ------------------- | -------------------- | ---- |
 `pull` | ❌ 拉取失败 | 2025-09-20 13:52:01 |  |
 `pull` | ❌ 拉取失败 | 2025-09-20 13:52:00 |  |
 `pull` | ❌ 拉取失败 | 2025-09-20 13:52:00 |  |
 `pull` | ❌ 拉取失败 | 2025-09-20 13:51:59 |  |
 `ghcr.io/tardlk/python:3.11` | ❌ 拉取失败 | 2025-09-20 13:51:59 |  |
 `ghcr.io/tardlk/postgres:15` | ❌ 拉取失败 | 2025-09-20 13:52:00 |  |
 `ghcr.io/tardlk/node:20` | ❌ 拉取失败 | 2025-09-20 13:52:01 |  |
 `ghcr.io/tardlk/mysql:8.0` | ❌ 拉取失败 | 2025-09-20 13:52:01 |  |
 `docker` | `docker pull ghcr.io/tardlk/docker` | 2025-09-20 13:52:01 |  |
 `docker` | `docker pull ghcr.io/tardlk/docker` | 2025-09-20 13:52:00 |  |
 `docker` | `docker pull ghcr.io/tardlk/docker` | 2025-09-20 13:52:00 |  |
 `docker` | `docker pull ghcr.io/tardlk/docker` | 2025-09-20 13:51:59 |  |
<!--SYNC-TABLE-END-->
