# Code Router注册与使用教程

[toc]

## 环境准备
* [Git](https://git-scm.com/downloads/win)
* NodeJs 18+
* [Nvm](https://github.com/coreybutler/nvm-windows/releases)

### 安装NVM
> Windows 11 安装过程中最好不要修改安装路径
```ps1
# 查看安装版本
nvm list available

# 安装
nvm install 20.19.5

# 查看
npm ls

# 使用
nvm use 20.19.5

# 查看版本
node -v
npm -v
```

### 安装Git
> 静默安装Git即可，配置下面的环境变量
```shell
变量名：CLAUDE_CODE_GIT_BASH_PATH
变量值：D:\Program Files\Git\bin\bash.exe

注意：D:\Program Files\Git\bin\bash.exe为Git安装地址下的bash工具

# 设置方法：
1. 右键"此电脑" → "属性" → "高级系统设置" → "环境变量"
2. 在"系统变量"区域点击"新建"
3. 分别添加上述变量
4. 点击"确定"保存所有更改
```

### 注册Code Router
注册地址:https://api.codemirror.codes/register

使用Github账号注册，直接登录即可

### 使用Code Router领取100$
```ps1
左侧边栏 -> "令牌管理"
"添加令牌" -> 额度设置为"100$"
模型限制为claude sonnet 4.5和4
```

### 配置使用环境（Windows PowerShell管理员运行）
```ps1
# 安装claude-code
npm install -g @anthropic-ai/claude-code

# 在Code Router获取API密钥
sk-GQSvewerxxxxsadwqkqUIW

# 需要设置的环境变量：
Claude Code配置：
变量名：ANTHROPIC_BASE_URL
变量值：https://api.codemirror.codes/
变量名：ANTHROPIC_API_KEY
变量值：你的密钥
变量名：ANTHROPIC_AUTH_TOKEN
变量值：你的密钥

# 设置方法：
1. 右键"此电脑" → "属性" → "高级系统设置" → "环境变量"
2. 在"系统变量"区域点击"新建"
3. 分别添加上述三个变量
4. 点击"确定"保存所有更改

# 验证
claude -v

claude : 无法加载文件 C:\nvm4w\nodejs\claude.ps1，因为在此系统上禁止运行脚本。有关详细信息，请参阅 https:/go.microsoft.
com/fwlink/?LinkID=135170 中的 about_Execution_Policies。
所在位置 行:1 字符: 1
+ claude -v
+ ~~~~~~
    + CategoryInfo          : SecurityError: (:) []，PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

# 解决报错：修改 PowerShell 执行策略
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# 执行验证
claude -v
2.0.22 (Claude Code)
```

### Claude Code终端使用（Windows PowerShell管理员运行）
```ps1
claude


╭─── Claude Code v2.0.22 ─────────────────────────────────────────────────────────────────────────────────────────────╮
│                                    │ Tips for getting started                                                       │
│            Welcome back!           │ Run /init to create a CLAUDE.md file with instructions for Claude              │
│                                    │ ─────────────────────────────────────────────────────────────────              │
│               ▐▛███▜▌              │ Recent activity                                                                │
│              ▝▜█████▛▘             │ No recent activity                                                             │
│                ▘▘ ▝▝               │                                                                                │
│                                    │                                                                                │
│   Sonnet 4.5 · API Usage Billing   │                                                                                │
│        C:\Windows\system32         │                                                                                │
╰─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯

───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
> Try "fix typecheck errors"
───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
  ? for shortcuts                                                                                                                                                                    Thinking off (tab to toggle)

# 提示：Try "fix typecheck errors"中输入问题即可
```
**补充：claude code命令（https://zhuanlan.zhihu.com/p/1928918331810886674）**
