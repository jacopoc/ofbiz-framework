<!---
 Licensed to the Apache Software Foundation (ASF) under one or more
 contributor license agreements.  See the NOTICE file distributed with
 this work for additional information regarding copyright ownership.
 The ASF licenses this file to You under the Apache License, Version 2.0
 (the "License"); you may not use this file except in compliance with
 the License.  You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
-->

# Contributing to Apache OFBiz

Thank you for your interest in contributing to the Apache OFBiz project! Community contributions help improve the project for everyone. This document outlines the typical workflow used to submit code, documentation, and other improvements.

## Before You Start

Apache projects follow a few common practices:

* Code must comply with the **Apache License 2.0** requirements.
* Source files should include the appropriate **Apache license header** where applicable.
* Contributions are submitted through **GitHub Pull Requests**.
* For larger changes, opening an issue or discussion first is recommended but **not required**.

## Contribution Workflow

### 1. Fork the Repository

Fork the repository to your GitHub account:

https://github.com/apache/ofbiz-framework

Click **Fork** in the top-right corner of the page.

### 2. Clone Your Fork

Clone your fork locally:

```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/ofbiz-framework.git
cd ofbiz-framework
```

Optionally add the upstream repository:

```bash
git remote add upstream https://github.com/apache/ofbiz-framework.git
```

### 3. Create a Branch

Create a dedicated branch for your work:

```bash
git switch -c my-feature-or-fix
```

Use a short but descriptive branch name.

### 4. Make Your Changes

Implement your fix, improvement, or feature.

Please try to:

* Follow the existing coding style
* Keep changes small and focused
* Ensure the project builds successfully
* Add or update tests when appropriate
* Avoid unrelated refactoring in the same pull request

### 5. Commit Your Changes

Write clear and descriptive commit messages.

Example:

```
Fix rounding issue in order calculation

- Correct rounding logic in OrderServices
- Add test covering edge case
```

### 6. Push Your Branch

Push your branch to your fork:

```bash
git push origin my-feature-or-fix
```

### 7. Open a Pull Request

Open a Pull Request against the **trunk branch** of the Apache OFBiz repository.

Include:

* A clear description of the change
* The motivation for the change
* Any relevant context or testing information

### 8. Review Process

Project maintainers and community members will review your pull request.

You may be asked to:

* Clarify parts of the implementation
* Update code style
* Make additional improvements

Please update your branch and push changes to the same pull request.

Once the review is complete and approved, the contribution will be merged.

## Contributing to Release Branches (Backports)

In some cases, a fix may also need to be applied to a maintained **release branch**.

The recommended approach is:

1. **Apply the fix to `trunk` first**
2. **Backport the change to the release branch**

This keeps the main development branch as the source of truth.

### Backport Workflow

1. Identify the commit that was merged into `trunk`.

2. Create a branch starting from the target release branch.

Example for `release24.09`:

```bash
git switch release24.09
git switch -c backport-my-fix-24.09
```

3. Cherry-pick the original commit:

```bash
git cherry-pick -x <commit-sha>
```

The `-x` flag automatically records the original commit reference.

4. Resolve any conflicts if necessary and ensure the project builds correctly.

5. Push the branch and open a Pull Request targeting the **release branch**:

```bash
git push origin backport-my-fix-24.09
```

In the Pull Request description, reference the original commit from `trunk`.

### Backport Guidelines

* Prefer fixing **trunk first**, then backporting.
* Backports should typically include **bug fixes or critical improvements**.
* Avoid introducing new features into release branches.
* Keep backport pull requests small and focused.

## Keeping Your Fork Updated

To synchronize your fork with the upstream repository:

```bash
git fetch upstream
git switch trunk
git merge upstream/trunk
```

## Pull Request Checklist

Before submitting a PR, please verify that:

* The code builds successfully
* Tests pass (if applicable)
* Changes are focused and minimal
* Commit messages clearly describe the change
* Documentation is updated when necessary

## Documentation Contributions

Documentation improvements are always welcome. This includes:

* Fixing typos or unclear explanations
* Improving examples
* Expanding guides or developer documentation

Documentation-only pull requests follow the same workflow described above.

## Thank You

Your contributions help improve Apache OFBiz for the entire community. Thank you for being part of the project!
