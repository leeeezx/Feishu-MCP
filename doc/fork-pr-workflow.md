# Fork & Pull Request 开发工作流指南

本指南旨在帮助开发者（特别是初学者）了解如何参与 `Feishu-MCP` 项目的协作开发。

## 1. 核心流程概览

由于你没有直接修改原作者仓库（Upstream）的权限，标准的协作流程如下：

1. **Fork**: 在 GitHub 上复制一份项目到你的个人账号。
2. **Clone & Setup**: 将你的仓库下载到本地，并配置关联原作者仓库。
3. **Branch**: 为每个新功能或修复创建一个独立的分支。
4. **Develop**: 在本地编写代码、测试并提交（Commit）。
5. **Push**: 将分支推送到你的 GitHub 仓库（Origin）。
6. **Pull Request (PR)**: 在 GitHub 上请求原作者合并你的改动。

***

## 2. 本地 Git 配置 (已完成)

你目前的本地环境已经配置好了两个远程连接：

* **`origin`**: 指向你的 Fork 仓库 (`https://github.com/leeeezx/Feishu-MCP.git`)。
* **`upstream`**: 指向原作者的仓库 (`https://github.com/cso1z/Feishu-MCP.git`)。

可以通过以下命令查看：

```Shell
git remote -v
```

***

## 3. 日志开发步骤

### 第一步：同步最新代码

在开始任何新工作前，确保你的本地代码是最新的：

```Shell
# 切换到主分支
git checkout main
# 从原作者仓库拉取最新代码
git pull upstream main
# 同步到你的 GitHub 仓库
git push origin main
```

### 第二步：创建开发分支

**永远不要直接在** **`main`** **分支上改代码！**

```Shell
# 创建并切换到新分支（名字要反映你做的事情）
git checkout -b feat-new-tool  # 例如添加新工具
# 或
git checkout -b fix-bug-name   # 例如修复某个 bug
```

### 第三步：编写代码并提交

修改文件后，保存并提交：

```Shell
# 查看改动了哪些文件
git status
# 添加改动
git add .
# 提交并说明原因
git commit -m "feat: 描述你添加的功能"
```

### 第四步：推送分支

将你的本地分支推送到你的 GitHub 仓库：

```Shell
git push origin <你的分支名>
```

***

## 4. 发起 Pull Request (PR)

1. 打开浏览器，进入你的 GitHub 仓库页面。
2. 你会看到一个黄色的提示条：`Your-branch-name had recent pushes...`。
3. 点击旁边的 **"Compare & pull request"**。
4. 在标题和描述中清晰地说明：
   * **WHY**: 为什么要改？（修复了什么问题，或者增加了什么需求）
   * **WHAT**: 改了哪些地方？
5. 点击 **"Create pull request"**。

***

## 5. 常用开发命令

* **安装依赖**: `pnpm install`
* **本地运行（开发模式）**: `pnpm run dev`
* **构建项目**: `pnpm run build`
* **代码格式化**: `pnpm run format`

祝开发愉快！
