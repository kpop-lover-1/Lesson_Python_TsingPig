## 一、DevHints.io —— 全能开发者速查手册

### 🔗 官网

- [https://devhints.io](https://devhints.io/)

### 📁 GitHub 仓库

- [https://github.com/rstacruz/cheatsheets](https://github.com/rstacruz/cheatsheets)

### 🎯 定位

提供简洁、美观、结构化的**技术速查表（cheatsheets）**，覆盖编程语言、工具、框架、系统命令等。

---

### ✅ 核心特点

|特性|说明|
|---|---|
|**内容广**|包含 Git、Bash、Python、Docker、HTTP、Regex、Linux 命令等 100+ 主题|
|**极简设计**|每页只展示最常用、最关键的用法，无冗余信息|
|**响应式网页**|适配手机、平板、桌面，阅读体验优秀|
|**开源免费**|MIT 协议，可自由使用、修改、部署|
|**支持多语言**|部分页面提供中文（如 Bash、Git）|

---

### 🧰 使用方式

#### 1. **在线查阅（推荐）**

直接访问 [https://devhints.io](https://devhints.io/)，点击左侧菜单选择主题。

示例：

- Git：[https://devhints.io/git](https://devhints.io/git)
- Bash：[https://devhints.io/bash](https://devhints.io/bash)
- Python：[https://devhints.io/python](https://devhints.io/python)

#### 2. **离线使用**

- 点击页面右上角 **“Download as PDF”** 保存为 PDF
- 或克隆 GitHub 仓库，本地构建：
```
    git clone https://github.com/rstacruz/cheatsheets.git
    cd cheatsheets
    # 内容在 /pages/ 目录下，均为 .md 文件
```
#### 3. **贡献新速查表**
- 在 GitHub 提交 Issue：[Request a cheatsheet](https://github.com/rstacruz/cheatsheets/issues/907)
- 或直接提交 PR（需遵循 Markdown 格式）

---

### 💡 使用场景

- 初学某工具（如 Docker），快速掌握核心命令
- 忘记正则语法，5 秒内查到 `(?=...)` 含义
- 团队培训时作为参考资料分发

---

## 二、tldr-pages —— 终端命令极简指南

### 🔗 官网

- [https://tldr.sh](https://tldr.sh/)

### 📁 GitHub 仓库

- [https://github.com/tldr-pages/tldr](https://github.com/tldr-pages/tldr)

### 🎯 定位

为命令行工具提供**简化版 man 手册**，口号是：“Too Long; Didn’t Read”。

> 替代冗长的 `man` 文档，只告诉你“怎么用”。

---

### ✅ 核心特点

|特性|说明|
|---|---|
|**专注 CLI**|覆盖 4000+ 命令（如 `grep`, `curl`, `tar`, `ffmpeg`）|
|**社区维护**|全球开发者共同编写，持续更新|
|**多平台支持**|Linux、macOS、Windows（WSL 或 PowerShell）|
|**本地 CLI 工具**|可安装命令行客户端，直接在终端查询|
|**多语言支持**|中文、日文、法语等（需配置）|

---

### 🧰 使用方式

#### 1. **安装 tldr 客户端（推荐）**

##### ▶️ 方法一：通过 npm（需 Node.js）
```
npm install -g tldr
```
##### ▶️ 方法二：通过包管理器
```
# macOS (Homebrew)
brew install tldr

# Ubuntu/Debian
sudo apt install tldr

# Windows (Scoop)
scoop install tldr
```

#### 2. **基本用法**
```
# 查看命令用法
tldr git
tldr curl
tldr tar

# 查看特定平台的用法（如 Linux vs macOS）
tldr --platform linux ls

# 更新缓存（默认每周自动更新）
tldr --update
```
#### 3. **离线使用**
- 首次运行会自动下载压缩包（约 10MB）
- 数据存储在 `~/.tldr` 目录，无需联网即可查询
#### 4. **查看中文（如支持）**
```
# 设置语言环境（部分命令有中文）
export TLDR_LANGUAGE=zh
tldr git
```

> ⚠️ 注意：中文覆盖率约 60%，英文更全。

---

### 📄 示例输出（`tldr tar`）
```
tar

Archiving utility.
Commonly used to compress or decompress files.

- Create an archive from files:
  tar cf target.tar file1 file2 file3

- Extract an archive in current directory:
  tar xf source.tar

- Create a gzipped archive:
  tar czf target.tar.gz file1 file2

- Extract a gzipped archive:
  tar xzf source.tar.gz
```

> ✅ 对比 `man tar`（数百行）—— tldr 只给最常用的 4 行！

---
### 💡 使用场景
- 在服务器上忘记 `tar` 解压参数，秒查
- 学习新命令（如 `jq`、`rsync`）快速上手
- 自动化脚本前快速确认命令语法

---

## 三、对比总结

|项目|DevHints.io|tldr-pages|
|---|---|---|
|**目标用户**|所有开发者（前端/后端/运维）|命令行重度用户|
|**内容范围**|广（语言 + 工具 + 协议）|窄而深（仅 CLI 命令）|
|**使用入口**|浏览器网页|终端命令（`tldr xxx`）|
|**是否需安装**|否（在线即可）|推荐安装 CLI 工具|
|**最佳搭配**|学习新技术、写文档参考|日常终端操作、调试|

---

## 四、推荐工作流

---

## 五、附录：常用链接收藏

- DevHints.io: [https://devhints.io](https://devhints.io/)
- tldr 官网: [https://tldr.sh](https://tldr.sh/)
- DevHints GitHub: [https://github.com/rstacruz/cheatsheets](https://github.com/rstacruz/cheatsheets)
- tldr GitHub: [https://github.com/tldr-pages/tldr](https://github.com/tldr-pages/tldr)
- tldr 中文进度: [https://github.com/tldr-pages/tldr/tree/main/translations/zh](https://github.com/tldr-pages/tldr/tree/main/translations/zh)

---

✅ **建议**：将本笔记保存为 `dev-cheatsheets-guide.md`，并加入你的个人知识库。  
🚀 让查命令不再翻 `man`，让学技术不再读长文！

# 平时的使用方法也这样给我
**DevHints.io 与 tldr-pages 日常使用方法笔记**
# 🛠️ DevHints.io 与 tldr-pages —— 日常使用方法速查

> 面向实际工作流：写代码、配环境、调命令、查语法  
> ✅ 无需死记硬背，用时即查

---

## 一、tldr-pages：终端里的“救命稻草”

### ✅ 场景 1：忘记某个命令怎么用（最常见！）

```
# 忘了 tar 怎么解压 .tar.gz？
tldr tar

# 忘了 rsync 同步目录的参数？
tldr rsync

# 忘了 curl 发 POST 请求？
tldr curl
```

> 💡 输出直接给出 **可复制的示例命令**，省去读 `man` 的时间。

---

### ✅ 场景 2：在服务器上临时操作（无图形界面）
```
# 登录远程 Linux 服务器
ssh user@server

# 安装 tldr（如果未预装）
sudo apt update && sudo apt install -y tldr  # Debian/Ubuntu
# 或
brew install tldr  # macOS

# 立即查询
tldr grep      # 查找日志关键词
tldr find      # 找文件
tldr chmod     # 改权限
```

> ⚠️ 注意：部分精简系统（如 Alpine）需先装 Node.js 或用 `apk add tldr`。

---

### ✅ 场景 3：学习新命令（如 `jq`, `ffmpeg`）
```
# 第一次用 jq 解析 JSON
tldr jq

# 输出示例：
# Parse JSON from stdin and print it
#   echo '{"name":"John"}' | jq '.'

# 提取字段
#   cat data.json | jq '.name'
```

> ✅ 比官方文档更快上手！

---

### ✅ 场景 4：更新缓存（确保用最新版）
```
# 手动更新（默认每周自动更新）
tldr --update

# 清除缓存（遇到显示异常时）
rm -rf ~/.tldr
```

---
### ✅ 小技巧

|技巧|命令|
|---|---|
|查看所有支持的命令|`tldr --list`|
|搜索关键词（如含 "zip" 的命令）|`tldr --search zip`|
|强制英文（避免中文翻译不全）|`TLDR_LANGUAGE=en tldr git`|

---

## 二、DevHints.io：浏览器里的“技术百宝箱”

### ✅ 场景 1：写代码时查语法（如正则、Python、Git）

1. 打开浏览器
2. 访问：
    - 正则：[https://devhints.io/regex](https://devhints.io/regex)
    - Python：[https://devhints.io/python](https://devhints.io/python)
    - Git：[https://devhints.io/git](https://devhints.io/git)
3. 复制粘贴常用片段

> 🌰 例如：
> 
> - 忘了 Python 列表推导式？→ 查 `python` 页
> - 不确定 HTTP 状态码？→ 查 `http` 页

---

### ✅ 场景 2：配置新工具（如 Docker、Nginx）

- Docker 常用命令：[https://devhints.io/docker](https://devhints.io/docker)
- Nginx 配置速查：[https://devhints.io/nginx](https://devhints.io/nginx)
- Bash 脚本语法：[https://devhints.io/bash](https://devhints.io/bash)

> 💡 比 Stack Overflow 更结构化，比官方文档更聚焦。

---

### ✅ 场景 3：教学/分享时提供参考资料

- 给新人培训 Git？直接分享：[https://devhints.io/git](https://devhints.io/git)
- 团队统一规范？把 `regex.md` 或 `yaml.md` 打印出来贴墙上 😄

---

### ✅ 场景 4：离线备用（网络差时）

1. 打开任意 DevHints 页面（如 [https://devhints.io/linux](https://devhints.io/linux)
    
    ）
    
2. 浏览器菜单 → **打印 → 另存为 PDF**
3. 保存到本地（如 `~/cheatsheets/linux.pdf`）

> 📁 建议建一个 `cheatsheets/` 文件夹，存放常用 PDF。

---

## 三、组合使用：效率翻倍！

### 🔄 典型工作流

|步骤|工具|操作|
|---|---|---|
|1. 在终端操作|`tldr`|`tldr ssh` → 快速连服务器|
|2. 写部署脚本|DevHints|查 `bash.md` 和 `linux.md`|
|3. 调 API|DevHints|查 `curl.md` + `http.md`|
|4. 解析日志|`tldr`|`tldr awk` / `tldr sed`|

---

### 💡 终极建议

- **终端党**：必装 `tldr`，每天用 3 次以上
- **全栈开发者**：把 DevHints 加入浏览器书签栏
- **学生/新手**：两者结合 = 免费的“编程外挂”

---

## 四、附：快速安装 & 验证

### 安装 tldr（任选其一）

```
# 方法1: npm（通用）
npm install -g tldr

# 方法2: 包管理器
brew install tldr          # macOS
sudo apt install tldr      # Ubuntu/Debian
scoop install tldr         # Windows (Scoop)
```

### 验证是否成功


```
tldr --version    # 应输出版本号
tldr ls           # 应显示 ls 用法
```

> ✅ 成功后，你已拥有“命令行外挂”！

---

## 五、常见问题（FAQ）

**Q：tldr 没有中文怎么办？**  
A：部分命令有中文，可尝试 `export TLDR_LANGUAGE=zh`；若无，用英文版（更全）。

**Q：DevHints 打不开？**  
A：可能是网络问题，可访问 GitHub 源文件：  
→ [https://github.com/rstacruz/cheatsheets/tree/master/pages](https://github.com/rstacruz/cheatsheets/tree/master/pages)

**Q：能自建私有速查表吗？**  
A：可以！克隆 DevHints 仓库，修改 `/pages/` 下的 `.md` 文件，用静态站点部署。

---

✅ **总结一句话**：

> **`tldr` 用于“终端里查命令”，DevHints 用于“浏览器里学技术”——二者互补，缺一不可。**

---

🔖 建议保存为：`daily-usage-cheatsheets.md`  
🚀 让你的开发效率，从“查文档”升级为“秒查秒用”！