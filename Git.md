---
layout: page
title: GitFluence
permalink: /GitFluence/
---

# Git Fluency

The absolute minimum PREREQUISITE for any serious attempt at engineering an asynchronous workflow is going to be commitment to improving your fluency in [Git commands](https://git-scm.com/docs/git) and that fluency will have to be grounded in a firm understanding of [Git concepts](https://git-scm.com/docs/user-manual#git-concepts) ... we have a strong preference for the [Git CLI](https://git-scm.com/docs/git) over GUIs, but we are not terribly dogmatic about this -- it's just that you even if your don't use the CLI, you will still need to understand what is happening *under the hood*.

## Git Butler, Tauri and Rust

In a nutshell, [GitButler](https://gitbutler.com/) is a more flexible version of git add -p and git rebase -i, allowing you to efficiently multitask across branches ... which is almost necessary capability for anyone with others in an asynchronous workflow. GitButler keeps track of uncommitted changes in a layer on top of Git. Changes to files or parts of files can be grouped into ***virtual branches***. Whenever you are happy with the contents of a virtual branch, you can push it to a remote. GitButler makes sure that the state of other virtual branches is kept separate.  

In using just Git alone, it is preferable or pretty much necessary when working with others, that you create your desired branches ahead of time, but when using GitButler you can move changes between ***virtual*** branches at any point during development.  *Normal* branches in Git are separate universes, and switching between them is a full context switch. 

GitButler allows you to work with multiple branches in parallel in the same working directory. This effectively means having the content of multiple branches available at the same time. GitButler is aware of changes before they are committed. This allows it to keep a record of which virtual branch each individual diff belongs to. Effectively, this means that you can separate out individual branches with their content at any time to push them to a remote or to unapply them from your working directory. 

For an asynchronous workflow, we ***strongly*** prefer [GitButler](https://gitbutler.com/) ... an [open source Git client](https://github.com/gitbutlerapp/gitbutler) for working on multiple branches at the same time. It allows you to quickly organize file changes into separate branches while still having them applied to your working directory. You can then push branches individually to your remote, or directly create pull requests. 

Strictly speaking, you do not absolutely NEED to use [GitButler](https://gitbutler.com/), ***although*** we strongly recommend doing so, and understanding WHY [open source Git client](https://github.com/gitbutlerapp/gitbutler) as well as understanding [why Tauri was built for security-focused, privacy-respecting, and environmentally-conscious software engineering community](https://tauri.app/v1/references/architecture/) and [how Tauri was used to build and debug GitButler in VSCode](https://blog.gitbutler.com/debugging-tauri-in-vs-code/).