---
comments: true
---

# Git 快速参考指南

## 创建目录（本地系统）

| **目的**                                                    | **命令**                              |
| ----------------------------------------------------------- | ------------------------------------- |
| 在家目录内创建一个新目录                                    | `cd -/目录名`                         |
| 创建一个新的 Git 仓库    添加单个文件或添加目录中的所有文件 | `git init`                            |
| 添加特定文件或添加所有文件                                  | `git add <文件名>` 或 `git add --all` |
| 克隆远程仓库                                                | `git clone <链接>`                    |

## 检查状态的命令

| **目的**             | **命令**     |
| -------------------- | ------------ |
| 显示已更改的文件     | `git status` |
| 显示已更改文件的差异 | `git diff`   |
| 显示日志文件         | `git log`    |

## 处理分支的命令

| **目的**                     | **命令**                   |
| ---------------------------- | -------------------------- |
| 显示当前所在的分支           | `git branch <分支名>`      |
| 创建一个新分支并切换到该分支 | `git checkout -b <分支名>` |
| 切换到一个已存在的分支       | `git checkout <分支名>`    |
| 删除一个已存在的分支         | `git branch d <分支名>`    |

## 撤销更改的命令

| **目的**               | **命令**              |
| ---------------------- | --------------------- |
| 通过提交ID撤销特定提交 | `git revert <提交ID>` |
| 撤销所有提交           | `git reset --hard`    |
| 撤销最后一次更改       | `git reset ^HEAD`     |
| 修正最后一次提交       | `git commit --amend`  |

## 发布更改的命令

| **目的**                       | **命令**                           |
| ------------------------------ | ---------------------------------- |
| 提交本地更改                   | `git commit -m "更新"`             |
| 提交本地更改（编辑单独的消息） | `git commit -a`                    |
| 推送更改到你的仓库             | `git push -u origin master/分支名` |
| 为其他开发者准备               | `git format-patch origin`          |
| 获取帮助                       | `git --help`                       |

[阅读更多](https://itsfoss.com/basic-git-commands-cheat-sheet/)