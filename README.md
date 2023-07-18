<div align="center">

<div align="center">

<img src="./pics/logo-dark.png#gh-dark-mode-only" width="250"/>
<img src="./pics/logo-light.png#gh-light-mode-only" width="250"/>

</div>

[![GitHub license](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://github.com/shivendrasoni/gitsensei/blob/main/LICENSE)
</div>
<div style="text-align:left;">

`Gitsensei` is a powerful tool designed to assist developers in reviewing PRs with greater speed and efficiency. It employs automated analysis techniques to evaluate the PR and offers various forms of feedback, ensuring a comprehensive review process.

**Auto-Description**: Automatically generating PR description - name, type, summary, and code walkthrough.
\
**PR Review**: Feedback about the PR main theme, type, relevant tests, security issues, focused PR, and various suggestions for the PR content.
\
**Question Answering**: Answering free-text questions about the PR.
\
**Code Suggestion**: Committable code suggestions for improving the PR.

<div align="left">

- [Overview](#overview)
- [Usage and tools](#usage-and-tools)
- [How it works](#how-it-works)
- [Roadmap](#roadmap)
</div>


---
## Overview
`Git-Sensei` offers extensive pull request functionalities across various git providers:

In the [configuration](./CONFIGURATION.md) file you can select your git provider (GitHub only for now, Gitlab, Bitbucket will be supported soon), and further configure the different tools.

## Install

- [Run as a GitHub Action](INSTALL.md#run-as-a-github-action)

## Usage and Tools

**Git-Sensei** provides four types of interactions ("tools"): `"PR Reviewer"`, `"PR Q&A"`, `"PR Description"` and `"PR Code Sueggestions"`.

- The "PR Reviewer" tool automatically analyzes PRs, and provides various types of feedback.
- The "PR Q&A" tool answers free-text questions about the PR.
- The "PR Description" tool automatically sets the PR Title and body.
- The "PR Code Suggestion" tool provide inline code suggestions for the PR that can be applied and committed.

## How it works

Check out the [PR Compression strategy](./PR_COMPRESSION.md) page for more details on how it converts a code diff to a manageable LLM prompt

## Roadmap

- [ ] Support open-source models, as a replacement for openai models. (Note - a minimal requirement for each open-source model is to have 8k+ context, and good support for generating json as an output)
- [ ] Support other Git providers, such as Gitlab and Bitbucket.
- [ ] Develop additional logics for handling large PRs, and compressing git patches
- [ ] Dedicated tools and sub-tools for specific programming languages (Python, Javascript, Java, C++, etc)
- [ ] Add additional context to the prompt. For example, repo (or relevant files) summarization, with tools such a [ctags](https://github.com/universal-ctags/ctags)
- [ ] Adding more tools. Possible directions:
  - [x] PR description
  - [x] Inline code suggestions
  - [ ] Enforcing CONTRIBUTING.md guidelines
  - [ ] Performance (are there any performance issues)
  - [ ] Documentation (is the PR properly documented)
  - [ ] Rank the PR importance
  - [ ] ...

# git-sensei
