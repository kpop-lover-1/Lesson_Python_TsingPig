# 计算机基础概念速查手册

## 1. 环境变量（Environment Variables）

环境变量是操作系统中用于存储配置信息的键值对，供程序运行时读取。

- 常见用途：指定程序路径、语言设置、临时目录等。
- 查看方式：
  - **Linux/macOS (Bash)**: `echo $PATH`
  - **Windows (CMD)**: `echo %PATH%`
  - **PowerShell**: `$env:PATH`

## 2. PATH 环境变量

`PATH` 是一个特殊的环境变量，包含多个目录路径，系统在这些目录中查找可执行命令。

- **分隔符**：
  - Unix/Linux/macOS：冒号 `:`
  - Windows：分号 `;`
- 示例：
  - Linux: `/usr/local/bin:/usr/bin`
  - Windows: `C:\Windows\System32;C:\Python39`

## 3. 绝对路径 vs 相对路径

| 类型 | 含义 | Linux 示例 | Windows 示例 |
|------|------|------------|--------------|
| 绝对路径 | 从根目录开始的完整路径 | `/home/user/file.txt` | `C:\Users\user\file.txt` |
| 相对路径 | 相对于当前工作目录 | `./docs/readme.md` 或 `docs/readme.md` | `.\\docs\\readme.md` |

- `.` 表示当前目录，`..` 表示上一级目录。

## 4. 包管理器（Package Managers）

用于自动化安装、更新和卸载软件。

| 平台/语言 | 包管理器 | 示例命令 |
|----------|--------|--------|
| Ubuntu/Debian | `apt` | `sudo apt install git` |
| Fedora | `dnf` | `sudo dnf install python3` |
| macOS | Homebrew (`brew`) | `brew install node` |
| Python | `pip` | `pip install requests` |
| Node.js | `npm` | `npm install express` |
| Windows | Chocolatey | `choco install vscode` |

## 5. 终端模拟器、Shell 与命令行工具

- **终端模拟器**：图形界面中运行命令行的程序（如 GNOME Terminal、Windows Terminal）。
- **Shell**：解释并执行命令的程序。
  - `bash`：最广泛使用的 Unix Shell
  - `zsh`：macOS 默认（自 Catalina 起）
  - `fish`：强调用户体验
- **Windows 命令行**：
  - `cmd.exe`：传统命令提示符
  - `PowerShell`：功能强大的脚本环境，支持对象管道
  - **WSL**：可在 Windows 上运行 Linux Shell（如 Bash）

## 6. 路径分隔符：`/` 与 `\`

- **Unix/Linux/macOS**：使用正斜杠 `/`（如 `/usr/bin`）
- **Windows**：传统使用反斜杠 `\`（如 `C:\Windows`），但现代系统也兼容 `/`
- 编程注意：在字符串中 `\` 是转义字符，常需写成 `\\` 或使用原始字符串（如 Python 的 `r"C:\path"`）

## 7. Unix、类 Unix、Linux 与 Windows

| 系统 | 说明 |
|------|------|
| **Unix** | 最早的多用户操作系统（AT&T 开发） |
| **类 Unix** | 行为兼容 Unix 的系统（如 Linux、BSD、macOS） |
| **Linux** | 开源内核，搭配 GNU 工具构成完整 OS（如 Ubuntu、CentOS） |
| **Windows** | 微软闭源系统，使用 NT 内核，权限/路径模型不同 |

## 8. 文件权限系统

### Unix/Linux 权限
- 三类用户：所有者（u）、组（g）、其他（o）
- 三种权限：读（r=4）、写（w=2）、执行（x=1）
- 示例：`chmod 755 script.sh` → 所有者 rwx，组和其他 rx

### Windows 权限
- 基于 ACL（访问控制列表），通过资源管理器或 `icacls` 命令管理

## 9. 编码（Character Encoding）

- **ASCII**：仅英文字符（0–127）
- **UTF-8**：变长 Unicode 编码，兼容 ASCII，推荐使用
- **GBK**：中文编码（旧版 Windows 简体中文）
- 建议：所有文本文件和项目统一使用 UTF-8 编码

## 10. 虚拟环境（Virtual Environments）

用于隔离项目依赖，避免版本冲突。

### Python 示例
```bash
# 创建
python -m venv myenv

# 激活
# Linux/macOS:
source myenv/bin/activate
# Windows (CMD):
myenv\Scripts\activate

# 退出
deactivate
```

其他语言也有类似机制（如 Node.js 的 `node_modules`、Conda 环境等）。



# 计算机基础概念速查手册（完善版）

## 1. 环境变量（Environment Variables）

环境变量是操作系统中用于存储配置信息的键值对，供程序运行时读取。

- **常见用途**：
    - 指定程序路径（如 `PATH`）
    - 设置语言/区域（如 `LANG=en_US.UTF-8`）
    - 配置临时目录（如 `TMPDIR` / `TEMP`）
    - 控制程序行为（如 `DEBUG=1`）
- **查看方式**：
    - **Linux/macOS (Bash/Zsh)**: `echo $VARIABLE` 或 `printenv VARIABLE`
    - **Windows (CMD)**: `echo %VARIABLE%`
    - **PowerShell**: `$env:VARIABLE`
- **设置方式**（临时）：
    - Bash/Zsh: `export VAR=value`
    - CMD: `set VAR=value`
    - PowerShell: `$env:VAR = "value"`

> 💡 提示：永久设置需修改 shell 配置文件（如 `~/.bashrc`）或系统环境变量面板。

---

## 2. PATH 环境变量

`PATH` 是一个特殊的环境变量，包含多个目录路径，系统在这些目录中查找可执行命令。

- **分隔符**：
    - Unix/Linux/macOS：冒号 `:`
    - Windows：分号 `;`
- **示例**：
    - Linux: `/usr/local/bin:/usr/bin:/bin`
    - Windows: `C:\Windows\System32;C:\Python39\Scripts`
- **添加路径**（临时）：
    - Linux/macOS: `export PATH=$PATH:/new/path`
    - Windows (CMD): `set PATH=%PATH%;C:\new\path`

> ⚠️ 安全提示：避免将当前目录（`.`）加入 `PATH`，防止恶意脚本执行。

---

## 3. 绝对路径 vs 相对路径

表格

|类型|含义|Linux 示例|Windows 示例|
|---|---|---|---|
|**绝对路径**|从根目录开始的完整路径|`/home/user/file.txt`|`C:\Users\user\file.txt`|
|**相对路径**|相对于当前工作目录|`docs/readme.md` 或 `../config.ini`|`docs\readme.md` 或 `..\config.ini`|

- `.` 表示当前目录，`..` 表示上一级目录。
- 在脚本中推荐使用绝对路径或基于 `$PWD`/`%CD%` 构造路径，避免依赖调用位置。

---

## 4. 包管理器（Package Managers）

用于自动化安装、更新和卸载软件。

表格

|平台/语言|包管理器|示例命令|
|---|---|---|
|Ubuntu/Debian|`apt`|`sudo apt update && sudo apt install git`|
|CentOS/RHEL|`yum` / `dnf`|`sudo dnf install python3`|
|macOS|Homebrew (`brew`)|`brew install node`|
|Python|`pip`|`pip install requests`|
|Node.js|`npm` / `yarn` / `pnpm`|`npm install express`|
|Rust|`cargo`|`cargo add serde`|
|Windows|Chocolatey / Scoop|`choco install vscode`|
|跨平台（容器）|Docker|`docker pull nginx`|

> 💡 建议：开发时优先使用项目级包管理（如 `requirements.txt` + `pip`，`package.json` + `npm`）。

---

## 5. 终端模拟器、Shell 与命令行工具

- **终端模拟器（Terminal Emulator）**：图形界面中运行命令行的程序
    
    - Linux: GNOME Terminal, Konsole, Alacritty
    - macOS: Terminal.app, iTerm2
    - Windows: Windows Terminal（推荐）、ConEmu
- **Shell**：解释并执行命令的程序
    
    - `bash`：最广泛使用的 POSIX 兼容 Shell
    - `zsh`：macOS 默认（自 Catalina 起），支持插件（如 Oh My Zsh）
    - `fish`：强调用户体验，语法更友好
    - `PowerShell`：跨平台（Windows/Linux/macOS），面向对象管道
- **Windows 命令行生态**：
    
    - `cmd.exe`：传统命令提示符（功能有限）
    - `PowerShell`：现代脚本环境（`.ps1` 脚本）
    - **WSL（Windows Subsystem for Linux）**：可在 Windows 上运行完整 Linux 发行版（如 Ubuntu），支持 Bash、Zsh 等

---

## 6. 路径分隔符：`/` 与 `\`

- **Unix/Linux/macOS**：使用正斜杠 `/`（如 `/usr/bin`）
- **Windows**：
    - 传统使用反斜杠 `\`（如 `C:\Windows`）
    - **但现代 API 和工具（包括 PowerShell、Python、Node.js）普遍兼容 `/`**
- **编程注意事项**：
    - 在字符串中 `\` 是转义字符（如 `\n` 表示换行）
    - 常见写法：
        - Python: `r"C:\path"`（原始字符串）或 `"C:/path"`
        - C/C++: `"C:\\path"` 或使用 `/`
        - JavaScript: 推荐使用 `/` 或 `path.join()`（Node.js）

> ✅ 最佳实践：在跨平台代码中，**始终使用 `/` 或语言提供的路径拼接函数**（如 Python 的 `os.path.join` 或 `pathlib`）。

---

## 7. Unix、类 Unix、Linux 与 Windows

表格

|系统|说明|
|---|---|
|**Unix**|1969 年由 AT&T Bell Labs 开发，多用户、多任务操作系统|
|**类 Unix（Unix-like）**|行为兼容 Unix 的系统，遵循 POSIX 标准（如 Linux、BSD、macOS）|
|**Linux**|1991 年 Linus Torvalds 开发的开源内核，搭配 GNU 工具构成完整 OS（如 Ubuntu、Debian、CentOS）|
|**Windows**|微软闭源系统，使用 NT 内核；路径、权限、换行符（`\r\n`）等与 Unix 不同|

> 🔄 趋势：Windows 通过 WSL 和 PowerShell 正逐步兼容 Unix 工具链。

---

## 8. 文件权限系统

### Unix/Linux 权限（基于 mode bits）

- **三类用户**：所有者（u）、所属组（g）、其他（o）
- **三种权限**：
    - 读（r = 4）
    - 写（w = 2）
    - 执行（x = 1）
- **常用命令**：
    - 查看：`ls -l file`
    - 修改：`chmod 755 script.sh` → 所有者 rwx，组和其他 rx
    - 更改所有者：`chown user:group file`

### Windows 权限（基于 ACL）

- 使用访问控制列表（ACL），精细控制用户/组权限
- 图形界面：右键 → 属性 → 安全
- 命令行：`icacls filename /grant User:F`（F = 完全控制）

---

## 9. 编码（Character Encoding）

- **ASCII**：7 位编码，仅支持英文（0–127）
- **UTF-8**：
    - 变长 Unicode 编码（1–4 字节）
    - **完全兼容 ASCII**
    - **现代 Web、Linux、macOS 默认编码**
- **GBK / GB2312**：中文编码（旧版 Windows 简体中文系统）
- **UTF-16 / UTF-32**：固定长度，常用于 Windows 内部和 Java

> ✅ **强烈建议**：
> 
> - 所有源代码、配置文件、日志使用 **UTF-8 without BOM**
> - HTML 中声明 `<meta charset="utf-8">`
> - 终端设置 UTF-8 支持（如 `LANG=en_US.UTF-8`）

---

## 10. 虚拟环境（Virtual Environments）

用于隔离项目依赖，避免“依赖地狱”。

### Python（`venv` / `virtualenv`）

bash

编辑

```
# 创建
python -m venv myenv

# 激活
# Linux/macOS:
source myenv/bin/activate
# Windows (CMD):
myenv\Scripts\activate
# Windows (PowerShell):
myenv\Scripts\Activate.ps1

# 退出
deactivate
```

### 其他语言

- **Node.js**：依赖自动隔离在项目 `node_modules/`，配合 `package-lock.json`
- **Rust**：`cargo` 自动管理依赖，无需显式虚拟环境
- **Conda**（Python/多语言）：
    
    bash
    
    编辑
    
    ```
    conda create -n myenv python=3.10
    conda activate myenv
    ```
    

> 💡 提示：将虚拟环境目录加入 `.gitignore`，只提交依赖清单（如 `requirements.txt`）。

---

## 新增条目

### 11. 换行符（Line Endings）

不同系统使用不同换行符：

- **Unix/Linux/macOS**：`\n`（LF, Line Feed）
- **Windows**：`\r\n`（CRLF, Carriage Return + Line Feed）
- **经典 Mac（< OS X）**：`\r`（CR）

> ⚠️ 问题：混用会导致 Git 显示整文件变更、脚本执行失败（如 `#!/bin/bash\r` 报错）  
> ✅ 解决：
> 
> - Git 配置：`git config --global core.autocrlf true`（Windows）或 `input`（macOS/Linux）
> - 编辑器设置：统一保存为 LF（推荐）

---

### 12. 进程、线程与并发模型（简要）

表格

|概念|说明|
|---|---|
|**进程（Process）**|独立运行的程序实例，拥有独立内存空间|
|**线程（Thread）**|进程内的执行单元，共享进程内存|
|**GIL（Python）**|全局解释器锁，限制同一时间只有一个线程执行 Python 字节码|
|**异步 I/O**|非阻塞模型（如 `async/await`），适合高并发 I/O 密集任务|

> 📌 开发建议：CPU 密集用多进程，I/O 密集用多线程或异步。

---

### 13. 常用命令速查（跨平台）

表格

|功能|Linux/macOS|Windows (CMD)|Windows (PowerShell)|
|---|---|---|---|
|查看当前目录|`pwd`|`cd`|`Get-Location` 或 `pwd`|
|列出文件|`ls -la`|`dir`|`Get-ChildItem` 或 `ls`|
|查看文件内容|`cat file`|`type file`|`Get-Content file`|
|查找进程|`ps aux \| grep name`|`tasklist \| findstr name`|`Get-Process name`|
|终止进程|`kill -9 PID`|`taskkill /PID PID`|`Stop-Process -Id PID`|