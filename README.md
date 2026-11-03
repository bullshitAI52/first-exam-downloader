# 第一试卷下载器 v0.39

个人私有归档，保存用户提供的 Windows 程序。此仓库不是原作者的官方项目，也不包含源代码。

## 文件与使用

- `第一试卷下载器v0.39.exe`：用户提供的程序，版本号来自文件名。
- 下载文件后，需要在 Windows 环境中使用；macOS 不能直接运行 Windows EXE。
- 本次仅归档，没有运行程序，没有验证下载功能、兼容性或安全性。使用前请进行安全扫描，不要随意授予管理员权限或输入敏感账号。

## 功能介绍

以下功能及环境信息根据用户提供的说明整理，尚未在本仓库归档过程中实测。

使用 **Python + PyQt6** 开发，提供说明中的本机环境为 **Windows 10 企业版 LTSC，21H2**。

大白话说，就是先按「学科 + 年级」把整个栏目的试卷目录录进本地 SQLite 数据库，再按版本、关键词筛选，勾选需要的试卷，自动按命名规则下载。

**数据库里只有你扫过的栏目。** 没扫过的栏目打开时是空的，表格中间会提示「点右上角更新题库」。这时先更新题库，再查询。

支持表头单击排序、指定下载路径、自定义重命名、多线程下载等。

## 基本使用方法

1. 选学科、年级 → 点 **更新题库**，等它扫描完并存进本地 SQLite 库。
2. 选版本、输入关键词 → 点 **查询**。
3. 勾选要的试卷 → 选保存目录 → 点 **开始下载**。

## 下载文件命名规则

可自由组合以下字段：`[学科]`、`[年级]`、`[版本]`、`[标题]`、`[日期]`、`[编号]`。

- 默认规则：`[版本]-[标题]`。
- 保存后的文件名示例：`人教版-2025学年三年级数学下册期中测试卷.rar`。
- 留空：只用试卷标题。
- 不认识的字段（例如 `[题名]`）：会描红提示，并退回成只用标题，不会静默出错。
- 同名文件自动加 ` (1)`、` (2)`，不覆盖已有文件。

组合示例：

- `[学科][年级]_[标题]` → `数学三年级_人教版2025学年…rar`
- `[日期]_[版本]_[标题]` → `2025-03-29_人教版_人教版2025学年…rar`
- `[标题]_[编号]` → 在标题后加编号，方便区分重名试卷。

## 来源与权限

原作者、发布页面、许可证尚未提供。本仓库保持私有，仅用于个人保存；未获得许可前不公开分发，不添加开源许可证。请合法使用下载内容，遵守来源网站的使用规则和版权要求。

## English

Private personal archive of the user-supplied **First Exam Paper Downloader v0.39** Windows executable. The version is inferred from its filename. This is not the original author's official repository and contains no source code.

Download the executable for use on Windows; macOS cannot run a Windows EXE directly. The program has not been executed, security-audited, or functionally tested here. Scan it before use and do not provide sensitive credentials or unnecessary administrator privileges.

### Features and environment

According to the user-supplied description, the application uses **Python + PyQt6**, with **Windows 10 Enterprise LTSC, 21H2** as the reported local environment. These claims have not been independently tested for this archive.

Scan a category by subject and grade to save its paper listings in a local SQLite database. Then filter by textbook edition and keywords, select papers, and download them with configurable filenames. The interface also supports sorting by clicking column headers, choosing a download directory, renaming, and multithreaded downloads.

The database contains **only categories you have scanned**. An unscanned category is empty and displays a prompt to click the top-right “Update question bank” button.

### Quick start

1. Choose a subject and grade, click **更新题库** (Update question bank), and wait for the scan to finish saving the listings locally.
2. Choose an edition, enter keywords, and click **查询** (Search).
3. Select the papers, choose a destination folder, and click **开始下载** (Start download).

### Filename templates

Use the actual Chinese field names in the application: `[学科]` (subject), `[年级]` (grade), `[版本]` (edition), `[标题]` (title), `[日期]` (date), and `[编号]` (ID).

- Default: `[版本]-[标题]`, for example `人教版-2025学年三年级数学下册期中测试卷.rar`.
- Leave the template blank to use only the paper title.
- An unknown field such as `[题名]` is highlighted in red, and naming falls back to the title only.
- Existing files are not overwritten: duplicate names receive ` (1)`, ` (2)`, and so on.
- Examples: `[学科][年级]_[标题]`, `[日期]_[版本]_[标题]`, or `[标题]_[编号]` to include an ID for easier distinction.

The original author, release URL and license are currently unknown. Keep this archive private until redistribution permission is confirmed. No open-source license is granted by this archive.
