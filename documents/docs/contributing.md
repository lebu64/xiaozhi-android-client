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

## Development Process

### Keeping in Sync with Main Repository

Before starting work, it's very important to ensure your local repository stays synchronized with the main project. Here are the steps to synchronize your local repository:

1. Switch to your main branch (`main`):

```bash
git checkout main
```

2. Pull the latest changes from the upstream repository:

```bash
git fetch upstream
```

3. Merge changes from the upstream main branch to your local main branch:

```bash
git merge upstream/main
```

4. Push the updated local main branch to your GitHub repository:

```bash
git push origin main
```

### Creating Branches

Before starting any work, make sure to create a new branch from the latest upstream main branch:

```bash
# Get the latest upstream code (as described in the previous section)
git fetch upstream
git checkout -b feature/your-feature-name upstream/main
```

When naming branches, you can follow these conventions:
- `feature/xxx`: New feature development
- `fix/xxx`: Bug fixes
- `docs/xxx`: Documentation updates
- `test/xxx`: Testing related work
- `refactor/xxx`: Code refactoring

### Coding Standards

We use Flutter's officially recommended code style guide. Before submitting code, please ensure your code meets the following requirements:

- Use 2 spaces for indentation
- Line length should not exceed 120 characters
- Use meaningful variable and function names
- Add documentation comments for public APIs
- Use Dart type system

We recommend using Flutter's static code analysis tools to help you follow coding standards:

```bash
# Use dart analyze to check code
flutter analyze
```

### Testing

Before submitting, make sure all tests pass:

```bash
flutter test
```

## Submitting Changes

### Pre-submission Checklist

Before submitting your code, please ensure you complete the following checks:

1. Does the code comply with Flutter coding standards
2. Have necessary test cases been added
3. Do all tests pass
4. Has appropriate documentation been added
5. Has the problem you planned to solve been resolved
6. Is it synchronized with the latest upstream code

### Submitting Changes

During development, develop the habit of making small, frequent commits. This makes your changes easier to track and understand:

```bash
# View changed files
git status

# Stage changes
git add lib/feature.dart test/feature_test.dart

# Commit changes
git commit -m "feat: add new feature X"
```

### Resolving Conflicts

If you encounter conflicts when trying to merge upstream changes, please follow these steps to resolve them:

1. First understand where the conflicts are:

```bash
git status
```

2. Open the conflicting file, you will see markers similar to the following:

```
Upstream code
```

3. Modify the file to resolve conflicts, remove conflict markers
4. After resolving all conflicts, stage and commit:

```bash
git add .
git commit -m "fix: resolve merge conflicts"
```

### Commit Specification

We use [Conventional Commits](https://www.conventionalcommits.org/) specification to format Git commit messages. Commit messages should follow this format:

```
<type>[optional scope]: <description>

[optional body]

[optional footer]
```

Common commit types include:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Changes that don't affect code meaning (such as whitespace, formatting, etc.)
- `refactor`: Code refactoring that neither fixes bugs nor adds features
- `perf`: Performance improvement code changes
- `test`: Adding or correcting tests
- `chore`: Changes to build process or auxiliary tools and libraries

For example:

```
feat(tts): Add new speech synthesis engine support

Add support for Baidu speech synthesis API, including the following features:
- Support for multiple voice options
- Support for speech rate and volume adjustment
- Support for mixed Chinese-English synthesis

Fixes #123
```

### Pushing Changes

After completing code changes, push your branch to your GitHub repository:

```bash
git push origin feature/your-feature-name
```

If you have already created a Pull Request and need to update it, simply push to the same branch again:

```bash
# After making more changes
git add .
git commit -m "refactor: improve code based on feedback"
git push origin feature/your-feature-name
```

### Synchronize Latest Code Before Creating Pull Request

Before creating a Pull Request, it's recommended to synchronize with the upstream repository again to avoid potential conflicts:

```bash
# Get the latest upstream code
git fetch upstream

# Rebase the latest upstream code onto your feature branch
git rebase upstream/main

# If conflicts occur, resolve conflicts and continue rebase
git add .
git rebase --continue

# Force push the updated branch to your repository
git push --force-with-lease origin feature/your-feature-name
```

Note: Using `--force-with-lease` is safer than directly using `--force`, as it prevents overwriting changes pushed by others.

### Creating Pull Request

When you complete feature development or issue fixes, please follow these steps to create a Pull Request:

1. Push your changes to GitHub:

```bash
git push origin feature/your-feature-name
```

2. Visit your forked repository page on GitHub, click the "Compare & pull request" button

3. Fill out the Pull Request form:
   - Use a clear title, following commit message format
   - Provide detailed information in the description
   - Reference related issues (using `#issue-number` format)
   - If this is work in progress, add `[WIP]` prefix to the title

4. Submit the Pull Request and wait for project maintainers to review

### Pull Request Lifecycle

1. **Creation**: Submit your PR
2. **CI Checks**: Automated testing and code style checks
3. **Code Review**: Maintainers will review your code and provide feedback
4. **Revision**: Modify your code based on feedback
5. **Approval**: Once your PR is approved
6. **Merge**: Maintainers will merge your PR into the main branch

## Documentation Contribution

If you want to improve project documentation, please follow these steps:

1. Follow the steps above to Fork the project and clone it locally

2. Documentation is located in the `documents/docs` directory, using Markdown format

3. Install documentation development dependencies:

```bash
cd documents
pnpm install
```

4. Start local documentation server:

```bash
pnpm docs:dev
```

5. Visit `http://localhost:5173/xiaozhi-android/` in your browser to preview your changes

6. After completing changes, submit your contribution and create a Pull Request

### Documentation Writing Guidelines

- Use clear, concise language
- Provide practical examples
- Provide detailed explanations for complex concepts
- Include appropriate screenshots or diagrams (when needed)
- Avoid excessive technical terminology, provide explanations when necessary
- Maintain consistent documentation structure

## Issue Reporting

If you discover a problem but cannot fix it temporarily, please [create an Issue](https://github.com/huangjunsen0406/xiaozhi-android/issues/new) on GitHub. When creating an Issue, please include the following information:

- Detailed description of the problem
- Steps to reproduce the problem
- Expected behavior and actual behavior
- Your operating system and Python version
- Relevant log output or error information

## Code Review

After submitting a Pull Request, project maintainers will review your code. During the code review process:

- Please wait patiently for feedback
- Respond promptly to comments and suggestions
- Make modifications and update your Pull Request when necessary
- Maintain polite and constructive discussions

### Handling Code Review Feedback

1. Carefully read all comments and suggestions
2. Respond to or change each point
3. If you disagree with a suggestion, politely explain your reasoning
4. After completing modifications, leave a message in the PR to notify the reviewer

## Becoming a Project Maintainer

If you consistently make valuable contributions to the project, you may be invited to become a project maintainer. As a maintainer, you will have permission to review and merge others' Pull Requests.

### Maintainer Responsibilities

- Review Pull Requests
- Manage issues
- Participate in project planning
- Answer community questions
- Help guide new contributors

## Code of Conduct

Please respect all project participants and follow this code of conduct:

- Use inclusive language
- Respect different viewpoints and experiences
- Gracefully accept constructive criticism
- Focus on the best interests of the community
- Show empathy towards other community members

## Frequently Asked Questions

### Where should I start contributing?

1. Check issues marked as "good first issue"
2. Fix errors or unclear parts in documentation
3. Add more test cases
4. Solve problems you discover during use

### My submitted PR hasn't received a response for a long time, what should I do?

Leave a message in the PR, politely asking if further improvements or clarifications are needed. Please understand that maintainers may be busy and need some time to review your contribution.

### What types of changes can I contribute?

- Bug fixes
- New features
- Performance improvements
- Documentation updates
- Test cases

## Acknowledgments

Thank you again for contributing to the project! Your participation is very important to us, let's work together to make android-xiaozhi better!

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
