# demo-gitbook

This repository contains a collection of tutorials with code samples that are aimed to get you started quickly with gitbook, each highlighting a different gitbook capability.

## Summary

- [demo-gitbook](#demo-gitbook)
  - [Summary](#summary)
  - [Getting Started](#getting-started)
    - [Setup](#setup)
    - [Edit book](#edit-book)
    - [Build and run](#build-and-run)

## Getting Started
  
Make sure you have the following prerequisites installed on your machine:

- TortoiseGit ([download](https://tortoisegit.org/))
<!-- Git ([download](https://git-scm.com/))-->
- nvm for Windows ([download](https://github.com/coreybutler/nvm-windows/releases/tag/1.1.8))r locally](https://docs.dapr.io/getting-started/install-dapr-selfhost/)

### Setup

- install nodejs

```shell
nvm install 10.14.1
nvm use 10.14.1
```

- install gitbook-cli

```shell
npm install -g gitbook-cli
```

- version verification

```shell
# nvm version
1.1.8

# node -v
v10.14.1

# gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```

### Edit book

```
// 建立目錄
mkdir gitbook

// 進入目錄
cd gitbook

// 初始化 gitbook
gitbook init
```

- 產生出來的`README.md` 是簡介, `SUMMARY.md` 是目錄結構,
可以參考<https://github.com/rockexe0000/demo-gitbook/tree/main/book_sources>

### Build and run

- to compile and build gitbook:

```shell
gitbook install
```

- run the gitbook

```shell
gitbook serve
```

Serving book on `http://localhost:4000`
