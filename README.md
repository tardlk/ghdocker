# 🚀 Docker 镜像工具箱：构建与同步

## ✨ 主要功能

- **双重核心**：集镜像的 **构建** 与 **同步** 功能于一身，满足不同场景的需求。
- **手动触发**：所有工作流均可在 Actions 页面通过简单的表单手动启动。
- **多架构支持**：轻松构建 `linux/amd64`, `linux/arm64`, `linux/arm/v7` 等多种 CPU 架构的镜像。
- **多仓库推送**：一次构建，自动将镜像推送到 GitHub Packages (`ghcr.io`) 和 Docker Hub。
- **自动更新**：为已同步的镜像提供每日自动更新机制，确保您使用的版本始终最新。
- **结果自动化**：工作流执行成功后，会自动更新本 `README.md` 文件中的镜像列表。
- **安全可靠**：通过 GitHub 的加密 Secrets 安全管理您的私人凭证，避免硬编码风险。

## 🛠️ 首次安装与配置

为了让所有功能正常工作，最安全、最推荐的使用方式是 **Fork 本项目**到您自己的 GitHub 账户下，然后完成以下一次性配置。

### 步骤 2: 配置仓库权限

:closed_lock_with_key: 这是让 Actions 能够自动修改 `README.md` 和管理镜像的关键。

1. 在您 Fork 后的仓库页面，点击 **"Settings"** -> **"Actions"** -> **"General"**。
2. 在 `Workflow permissions` 区域，选择 **"Read and write permissions"**。
3. 勾选 **"Allow GitHub Actions to create and approve pull requests"**。
4. 点击 **"Save"** 保存设置。

### 已同步的 Docker 镜像

|   | 源镜像 | pull 镜像 | 同步 | 更新时间 |
| ---- | -------- | --------- | ---- | -------- |
| 1  | [示例源镜像1] | `ghcr.io/用户名/镜像1` | ✔️ | 2024-01-01 |
| 2  | [示例源镜像2:alpine] | `ghcr.io/用户名/镜像2:alpine` | ✔️ | 2024-01-02 |

> 表格将由工作流自动维护，包含已同步的镜像信息、拉取命令、同步状态及更新时间。
