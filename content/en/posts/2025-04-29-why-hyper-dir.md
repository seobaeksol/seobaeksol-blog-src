+++
date = '2025-04-29T20:54:52+09:00'
draft = true
title = 'Why I Started Building a Windows File Explorer with Rust'
description = "The origin story of the Hyper-Dir project, and why I chose Rust, React, and Tauri — with a UI inspired by VSCode."
tags = ["Rust", "Tauri", "React", "File Explorer", "Project Story"]
categories = ["Dev Log"] 
+++

> A look into the motivation, technical stack, and UX design philosophy behind Hyper-Dir

## 🧩 Why I Wanted a Better File Explorer

The default Windows File Explorer is okay — but as a developer, I kept running into limitations.

- No tab support
- Poor keyboard navigation
- No built-in dual/multi-pane view
- Difficult to customize or extend

Eventually, I asked myself:

> “What if I just built my own?”

---

## 🚀 The Birth of Hyper-Dir

That’s how **Hyper-Dir** was born.  
Not just a file explorer, but one that’s **developer-friendly, lightning fast, extensible**, and _keyboard-first_.  
Inspired by tools like VSCode.

### Project Goals

- ✅ Full keyboard navigation
- ✅ Multiple panels & tabs
- ✅ Plugin-based extensibility
- ✅ Clean and intuitive UX
- ✅ Native-like performance

---

## 🛠 Why I Chose Rust, Tauri, and React

### 🦀 Rust

I was drawn to Rust for its performance and memory safety.  
Working with the file system, especially on Windows, requires low-level control — and **Rust gives that without sacrificing safety**.

### 🪟 Tauri

Compared to Electron, Tauri is:

- Lighter
- Faster
- More native-feeling

Best of all, it plays **beautifully with Rust**.

### ⚛️ React

For the frontend, I went with React.

- Fast development
- Huge ecosystem
- Well-suited for building extensible UI, like VSCode extensions

---

## 🧠 UI/UX Inspired by VSCode

Hyper-Dir's interface is heavily inspired by **Visual Studio Code**.

- **Sidebar** → Directory tree
- **Tab bar** → Navigate multiple folders
- **Main panel** → File list / preview
- **Status bar** → Path info, selection details
- **Shortcuts** → `Ctrl+P`, `Ctrl+B`, and more

> Developers are already familiar with VSCode.  
> A familiar layout means less friction and better usability.

---

## 🗺 Roadmap Ahead

Hyper-Dir is still early in development, but here’s what’s coming next:

- Git integration & embedded terminal
- Custom plugin system
- Favorites and history
- Advanced filtering & fuzzy search
- Extended command palette

---

## 💬 Closing Thoughts

As a developer, building the tools I use every day is incredibly rewarding.  
Hyper-Dir started as a way to solve my own pain points — but I hope it becomes a helpful tool for others too.

> Curious about the project or want to contribute?  
> Feedback, issues, and PRs are always welcome!

---

🧑‍💻 [Check out the GitHub repo](https://github.com/seobaeksol/hyper-dir)
