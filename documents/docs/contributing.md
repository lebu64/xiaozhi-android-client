---
title: Contribution Guide
description: How to contribute code to the android-xiaozhi project
sidebar: false
outline: deep
---

<div class="contributing-page">

# Contribution Guide

<div class="header-content">
  <h2>How to contribute code to the android-xiaozhi project 🚀</h2>
</div>

## Preface

Thank you for your interest in the android-xiaozhi project! We warmly welcome community members to participate in contributions, whether it's fixing bugs, improving documentation, or adding new features. This guide will help you understand how to submit contributions to the project.

## Development Environment Preparation

### Basic Requirements

- Flutter SDK 3.7.0 or higher
- Dart SDK 3.7.0 or higher
- Git version control system
- Android Studio or Visual Studio Code (with Flutter plugin)
- Android SDK (for Android development)
- Xcode (for iOS development, macOS only)

### Get Source Code

1. First, Fork this project to your own account on GitHub
   - Visit [android-xiaozhi project page](https://github.com/TOM88812/xiaozhi-android-client)
   - Click the "Fork" button in the top right corner
   - Wait for Fork to complete, you will be redirected to your repository copy

2. Clone your forked repository to local:

```bash
git clone https://github.com/YOUR_USERNAME/xiaozhi-android.git
cd xiaozhi-android-client
```

3. Add upstream repository as remote source:

```bash
git remote add upstream https://github.com/TOM88812/xiaozhi-android-client.git
```

You can use `git remote -v` command to confirm the remote repository is correctly configured:

```bash
git remote -v
# Should display:
# origin    https://github.com/YOUR_USERNAME/xiaozhi-android-client.git (fetch)
# origin    https://github.com/YOUR_USERNAME/xiaozhi-android-client.git (push)
# upstream  https://github.com/TOM88812/xiaozhi-android-client.git (fetch)
# upstream  https://github.com/TOM88812/xiaozhi-android-client.git (push)
```

### Install Development Dependencies

```bash
# Install Flutter dependencies
flutter pub get
```

## 开发流程

### 与主仓库保持同步

在开始工作之前，确保您的本地仓库与主项目保持同步是非常重要的。以下是同步本地仓库的步骤：

1. 切换到您的主分支（`main`）：

```bash
git checkout main
```

2. 拉取上游仓库的最新更改：

```bash
git fetch upstream
```

3. 将上游主分支的更改合并到您的本地主分支：

```bash
git merge upstream/main
```

4. 将更新后的本地主分支推送到您的 GitHub 仓库：

```bash
git push origin main
```

### 创建分支

在开始任何工作之前，请确保从最新的上游主分支创建新的分支：

```bash
# 获取最新的上游代码（如上节所述）
git fetch upstream
git checkout -b feature/your-feature-name upstream/main
```

为分支命名时，可以遵循以下约定：
- `feature/xxx`：新功能开发
- `fix/xxx`：修复 bug
- `docs/xxx`：文档更新
- `test/xxx`：测试相关工作
- `refactor/xxx`：代码重构

### 编码规范

我们使用 Flutter 官方推荐的代码风格指南。在提交代码前，请确保您的代码符合以下要求：

- 使用 2 个空格进行缩进
- 行长度不超过 120 个字符
- 使用有意义的变量和函数名称
- 为公共 API 添加文档注释
- 使用 Dart 类型系统

我们推荐使用 Flutter 的静态代码分析工具来帮助您遵循编码规范：

```bash
# 使用 dart analyze 检查代码
flutter analyze
```

### 测试

在提交之前，请确保所有测试都能通过：

```bash
flutter test
```

## 提交变更

### 提交前的检查清单

在提交您的代码之前，请确保完成以下检查：

1. 代码是否符合 Flutter 编码规范
2. 是否添加了必要的测试用例
3. 所有测试是否通过
4. 是否添加了适当的文档
5. 是否解决了您计划解决的问题
6. 是否与最新的上游代码保持同步

### 提交变更

在开发过程中，养成小批量、频繁提交的习惯。这样可以使您的更改更容易跟踪和理解：

```bash
# 查看更改的文件
git status

# 暂存更改
git add lib/feature.dart test/feature_test.dart

# 提交更改
git commit -m "feat: add new feature X"
```

### 解决冲突

如果您在尝试合并上游更改时遇到冲突，请按照以下步骤解决：

1. 首先了解冲突的位置：

```bash
git status
```

2. 打开冲突文件，您会看到类似以下标记：

```
上游代码
```

3. 修改文件以解决冲突，删除冲突标记
4. 解决完所有冲突后，暂存并提交：

```bash
git add .
git commit -m "fix: resolve merge conflicts"
```

### 提交规范

我们使用[约定式提交](https://www.conventionalcommits.org/zh-hans/)规范来格式化 Git 提交消息。提交消息应该遵循以下格式：

```
<类型>[可选 作用域]: <描述>

[可选 正文]

[可选 脚注]
```

常用的提交类型包括：
- `feat`：新功能
- `fix`：错误修复
- `docs`：文档更改
- `style`：不影响代码含义的变更（如空格、格式化等）
- `refactor`：既不修复错误也不添加功能的代码重构
- `perf`：提高性能的代码更改
- `test`：添加或修正测试
- `chore`：对构建过程或辅助工具和库的更改

例如：

```
feat(tts): 添加新的语音合成引擎支持

添加对百度语音合成API的支持，包括以下功能：
- 支持多种音色选择
- 支持语速和音量调节
- 支持中英文混合合成

修复 #123
```

### 推送更改

完成代码更改后，将您的分支推送到您的 GitHub 仓库：

```bash
git push origin feature/your-feature-name
```

如果您已经创建了 Pull Request，并且需要更新它，只需再次推送到同一分支即可：

```bash
# 在进行更多更改后
git add .
git commit -m "refactor: improve code based on feedback"
git push origin feature/your-feature-name
```

### 创建 Pull Request 前同步最新代码

在创建 Pull Request 前，建议再次与上游仓库同步，以避免潜在的冲突：

```bash
# 获取上游最新代码
git fetch upstream

# 将上游最新代码变基到您的特性分支
git rebase upstream/main

# 如果出现冲突，解决冲突并继续变基
git add .
git rebase --continue

# 强制推送更新后的分支到您的仓库
git push --force-with-lease origin feature/your-feature-name
```

注意：使用 `--force-with-lease` 比直接使用 `--force` 更安全，它可以防止覆盖他人推送的更改。

### 创建 Pull Request

当您完成功能开发或问题修复后，请按照以下步骤创建 Pull Request：

1. 将您的更改推送到 GitHub：

```bash
git push origin feature/your-feature-name
```

2. 访问 GitHub 上您 fork 的仓库页面，点击 "Compare & pull request" 按钮

3. 填写 Pull Request 表单：
   - 使用清晰的标题，遵循提交消息格式
   - 在描述中提供详细信息
   - 引用相关 issue（使用 `#issue编号` 格式）
   - 如果这是一个进行中的工作，请添加 `[WIP]` 前缀到标题

4. 提交 Pull Request，等待项目维护者审核

### Pull Request 的生命周期

1. **创建**：提交您的 PR
2. **CI 检查**：自动化测试和代码风格检查
3. **代码审核**：维护者会审核您的代码并提供反馈
4. **修订**：根据反馈修改您的代码
5. **批准**：一旦您的 PR 被批准
6. **合并**：维护者会将您的 PR 合并到主分支

## 文档贡献

如果您想改进项目文档，请按照以下步骤操作：

1. 按照上述步骤 Fork 项目并克隆到本地

2. 文档位于 `documents/docs` 目录下，使用 Markdown 格式

3. 安装文档开发依赖：

```bash
cd documents
pnpm install
```

4. 启动本地文档服务器：

```bash
pnpm docs:dev
```

5. 在浏览器中访问 `http://localhost:5173/xiaozhi-android/` 预览您的更改

6. 完成更改后，提交您的贡献并创建 Pull Request

### 文档编写准则

- 使用清晰、简洁的语言
- 提供实际示例
- 对复杂概念进行详细解释
- 包含适当的截图或图表（需要时）
- 避免技术术语过多，必要时提供解释
- 保持文档结构一致

## 问题反馈

如果您发现了问题但暂时无法修复，请在 GitHub 上[创建 Issue](https://github.com/huangjunsen0406/xiaozhi-android/issues/new)。创建 Issue 时，请包含以下信息：

- 问题的详细描述
- 重现问题的步骤
- 预期行为和实际行为
- 您的操作系统和 Python 版本
- 相关的日志输出或错误信息

## 代码审核

提交 Pull Request 后，项目维护者将会审核您的代码。在代码审核过程中：

- 请耐心等待反馈
- 及时响应评论和建议
- 必要时进行修改并更新您的 Pull Request
- 保持礼貌和建设性的讨论

### 处理代码审核反馈

1. 认真阅读所有评论和建议
2. 针对每个要点作出回应或更改
3. 如果您不同意某个建议，礼貌地解释您的理由
4. 修改完成后，在 PR 中留言通知审核者

## 成为项目维护者

如果您持续为项目做出有价值的贡献，您可能会被邀请成为项目的维护者。作为维护者，您将有权限审核和合并其他人的 Pull Request。

### 维护者的职责

- 审核 Pull Request
- 管理 issue
- 参与项目规划
- 回答社区问题
- 帮助引导新贡献者

## 行为准则

请尊重所有项目参与者，遵循以下行为准则：

- 使用包容性语言
- 尊重不同的观点和经验
- 优雅地接受建设性批评
- 关注社区最佳利益
- 对其他社区成员表示同理心

## 常见问题解答

### 我应该从哪里开始贡献？

1. 查看标记为 "good first issue" 的问题
2. 修复文档中的错误或不清晰的部分
3. 添加更多测试用例
4. 解决您自己在使用过程中发现的问题

### 我提交的 PR 已经很久没有回应了，我该怎么办？

在 PR 中留言，礼貌地询问是否需要进一步的改进或澄清。请理解维护者可能很忙，需要一些时间来审核您的贡献。

### 我可以贡献哪些类型的更改？

- 错误修复
- 新功能
- 性能改进
- 文档更新
- 测试用例
- 代码重构

## 致谢

再次感谢您为项目做出贡献！您的参与对我们非常重要，共同努力让 android-xiaozhi 变得更好！

</div>

<style>
.contributing-page {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem 1.5rem;
}

.contributing-page h1 {
  text-align: center;
  margin-bottom: 1rem;
}

.header-content {
  text-align: center;
}

.header-content h2 {
  color: var(--vp-c-brand);
  margin-bottom: 1rem;
}

.contributing-page h2 {
  margin-top: 3rem;
  padding-top: 1rem;
  border-top: 1px solid var(--vp-c-divider);
}

.contributing-page h3 {
  margin-top: 2rem;
}

.contributing-page code {
  background-color: var(--vp-c-bg-soft);
  padding: 0.2em 0.4em;
  border-radius: 3px;
}

.contributing-page pre {
  margin: 1rem 0;
  border-radius: 8px;
  overflow: auto;
}
</style>
