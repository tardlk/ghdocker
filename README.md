# 🐳 Docker 镜像同步到 GHCR

本仓库使用 GitHub Actions 自动将常用的 Docker 镜像同步到 [GitHub Container Registry (GHCR)](https://ghcr.io)，方便国内外环境快速拉取。

## ✨ 功能
- 每天定时同步一次（北京时间 10:00）
- 支持手动触发同步
- 自动检测镜像是否更新，避免重复推送
- 自动更新下方同步状态表
---

## 📋 镜像同步状态

<!--SYNC-TABLE-START-->
| 源镜像 | 同步后镜像 | 更新时间 | 备注 |
| ------ | ---------- | -------- | ---- |
| nginx:latest | ghcr.io/USERNAME/nginx:latest | - | - |
| redis:latest | ghcr.io/USERNAME/redis:latest | - | - |
| alpine:latest | ghcr.io/USERNAME/alpine:latest | - | - |
| busybox:latest | ghcr.io/USERNAME/busybox:latest | - | - |
| mysql:8.0 | ghcr.io/USERNAME/mysql:8.0 | - | - |
| postgres:15 | ghcr.io/USERNAME/postgres:15 | - | - |
| mongo:6.0 | ghcr.io/USERNAME/mongo:6.0 | - | - |
| python:3.11 | ghcr.io/USERNAME/python:3.11 | - | - |
| node:20 | ghcr.io/USERNAME/node:20 | - | - |
| golang:1.21 | ghcr.io/USERNAME/golang:1.21 | - | - |
<!--SYNC-TABLE-END-->
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
