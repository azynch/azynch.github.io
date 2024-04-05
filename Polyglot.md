---
layout: page
title: Polyglot
permalink: /Polyglot/
---

## Git Fluency

The absolute minimum PREREQUISITE for any serious attempt at engineering an asynchronous workflow is going to be commitment to improving your fluency in [Git commands](https://git-scm.com/docs/git) and that fluency will have to be grounded in a firm understanding of [Git concepts](https://git-scm.com/docs/user-manual#git-concepts) ... we have a strong preference for being aware of [Git Command Line Interface (CLI)](https://git-scm.com/docs/git) over just trusting the graphical user interfaces, particularly Windows and Node.JS interfaces, because ubiquitous easy to use [and never second-guess] attracts evil, but we are not terribly dogmatic about this -- the main point is that just that you even if your don't use the CLI, you will inevitably still need to understand some things about what is happening *under the hood*.

### Git Concepts

There's not really an substitute for an in-depth, intuitive understanding of [Git concepts](https://git-scm.com/docs/user-manual#git-concepts), why you use Git, and how Git works.  

[Understanding commit history](https://git-scm.com/docs/user-manual#understanding-commits) is based on a solid foundation of really understand the [object storage format](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects) and relationships in the git internal architecture of the four different types of objects: [commit object](https://git-scm.com/docs/user-manual#def_commit_object) links a physical state of a tree with a description of how we got there and why, [tree object](https://git-scm.com/docs/user-manual#def_tree_object) object contains a list of entries, each with a mode, object type, SHA-1 name, and name, sorted by name, [tag objects](https://git-scm.com/docs/user-manual#def_tag_object) are more focused on versioning, findability, and reproducibility but they can be used to incorporate a degree of trust and authenticity into overall system; tags contain an object, object type, tag name, the name of the person ("tagger") who created the tag, and a message, which may contain a signature and [blob objects](https://git-scm.com/docs/user-manual#def_blob_object) nothing but a binary blob defined entirely by its file data; of course, file data is the basis of what you are working on under version control system, but don’t refer to anything else or have attributes of any kind.  

### Git Butler, Tauri and Rust

In a nutshell, [GitButler](https://gitbutler.com/) is a more flexible version of git add -p and git rebase -i, allowing you to efficiently multitask across branches ... which is almost necessary capability for anyone with others in an asynchronous workflow. GitButler keeps track of uncommitted changes in a layer on top of Git. Changes to files or parts of files can be grouped into ***virtual branches***. Whenever you are happy with the contents of a virtual branch, you can push it to a remote. GitButler makes sure that the state of other virtual branches is kept separate.  

In using just Git alone, it is preferable or pretty much necessary when working with others, that you create your desired branches ahead of time, but when using GitButler you can move changes between ***virtual*** branches at any point during development.  *Normal* branches in Git are separate universes, and switching between them is a full context switch. 

GitButler allows you to work with multiple branches in parallel in the same working directory. This effectively means having the content of multiple branches available at the same time. GitButler is aware of changes before they are committed. This allows it to keep a record of which virtual branch each individual diff belongs to. Effectively, this means that you can separate out individual branches with their content at any time to push them to a remote or to unapply them from your working directory. 

For an asynchronous workflow, we ***strongly*** prefer [GitButler](https://gitbutler.com/) ... an [open source Git client](https://github.com/gitbutlerapp/gitbutler) for working on multiple branches at the same time. It allows you to quickly organize file changes into separate branches while still having them applied to your working directory. You can then push branches individually to your remote, or directly create pull requests. 

### Tauri and Rust

Strictly speaking, you would not absolutely NEED to use [GitButler](https://gitbutler.com/), ***HOWEVER*** we strongly recommend using GitButler itself and understanding some things about the code of the [open source Git client](https://github.com/gitbutlerapp/gitbutler) as well as understanding [why Tauri was built for security-focused, privacy-respecting, and environmentally-conscious software engineering community](https://tauri.app/v1/references/architecture/) and [how Tauri was used to build Rust code and debug GitButler in VSCode](https://blog.gitbutler.com/debugging-tauri-in-vs-code/).

Tauri is application toolkit written in Rust that allows for making tiny, blazingly fast Webview OS applications; Tauir is not a VM or virtualized environment OR a lightweight kernel wrapper. Instead, it directly uses [WRY](https://github.com/tauri-apps/wry) and [TAO](https://github.com/tauri-apps/tao) to do the heavy lifting in making system calls to the OS. [WRY](https://github.com/tauri-apps/wry) is a cross-platform WebView rendering library in Rust which is the cross-platform abstract layer responsible to determining which webview is used and how interactions are made. The [TAO](https://github.com/tauri-apps/tao) of cross-platform windowing [for all major desktop and mobile platforms] window creation library that supports menu bars and system trays. 

### Rust

Strictly speaking, you would not absolutely NEED to use the [Tauri architecture](https://github.com/tauri-apps/tauri/blob/dev/ARCHITECTURE.md) to build and improve toolchain apps for ASYNCHRONOUS workflows ... *but doing Rust right is going to result in tiny, secure, blazingly fast applications. The reason to use an application toolkit like Tauri is that most of pitfalls are taken out of your way and the [Tauri community](https://github.com/tauri-apps) is **very active** (2200 forks on GitHub) open source development community that is constantly improving the toolkit ... of course, if something better than Tauri comes along, you can pick up the ideas there.

A developer must first [learn something about Rust](https://doc.rust-lang.org/book/) and then install the prerequisite toolchains for creating a Tauri app and then dive in. At the very least this will entail [installing rust](https://doc.rust-lang.org/book/ch01-01-installation.html) & [cargo](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html), and most likely also a modern version of node.js and potentially another package manager. Some platforms may also require other tooling and libraries, but this has been documented carefully in the respective platform docs.