# OTP 靶标评估 Skill 安装与使用说明书

本文档为 **otp\-target\-assessment** WorkBuddy 技能包的部署、安装与使用指南，适用于本地直接使用、跨机器迁移及团队共享场景。该技能基于标准 WorkBuddy Skill 规范打包，支持解压即装、无需额外依赖，适配个人用户及团队项目协作。

## 一、本地现有环境说明

当前设备已完成 **otp\-target\-assessment** 技能的用户级安装，无需重复部署，可直接在任意 WorkBuddy 新会话中使用。

### 安装目录（用户级，全局跨项目生效）

```Plain Text
C:\Users\gkxiao\.workbuddy\skills\otp-target-assessment\
```

### 直接使用方式

开启新 WorkBuddy 会话，输入包含技能触发关键词的指令，系统将自动加载技能，按照标准8步流程执行，并输出中文HTML格式评估报告。

**触发关键词**：靶标评估、靶点评估、成药性、Tractability、OTP 评估、target prioritisation 等

**使用示例**：

- 评估 SIGLEC8 在慢性自发性荨麻疹的开发前景

- 用 OTP 流程评估 BTK 在 CSU 上的可成药性

- 帮我做靶标评估：PTGDR2 × CSU

## 二、Skill 分发包安装指南（跨机器/团队共享）

项目提供标准化压缩分发包 `output/otp-target-assessment.zip`，为纯静态技能目录包，**解压即装、无安装器、无第三方依赖**，可自由迁移、分享给其他用户。

### 2\.1 安装方式（二选一）

#### 方式一：用户级安装（推荐，个人全局生效）

安装后对当前设备所有 WorkBuddy 项目、所有会话生效，为个人通用配置。

1. 解压 `otp-target-assessment.zip`，获得同名文件夹`otp-target-assessment`

2. 将文件夹放置到用户技能根目录：

```Plain Text
C:\Users\<你的用户名>\.workbuddy\skills\otp-target-assessment\
```

最终有效路径需包含核心文件：`...\.workbuddy\skills\otp-target-assessment\SKILL.md`

#### 方式二：项目级安装（团队共享生效）

安装后仅当前项目仓库/工作区生效，适合团队多人协作共用同一技能配置。

1. 解压压缩包获得 `otp-target-assessment` 文件夹

2. 将文件夹放置到项目私有技能目录：

```Plain Text
<项目目录>\.workbuddy\skills\otp-target-assessment\
```

同一项目工作区的所有成员均可自动加载使用该技能。

### 2\.2 核心安装约束（必看）

以下规则为技能生效的必要条件，任意违规将导致技能加载失败、无法触发任务：

1. **目录名校验**：根目录名称必须严格为 `otp-target-assessment`，与 `SKILL.md` 头部配置的 `name` 字段完全一致，大小写、连字符、字符顺序不可修改。

2. **完整目录结构**：必须保留原始完整目录，包含 `SKILL.md`、`scripts/`、`references/`、`assets/`，禁止仅拷贝单个文件、删减目录或修改文件结构。

3. **会话生效规则**：安装/更新技能后，**必须新建 WorkBuddy 会话**，技能仅在会话启动时加载，旧会话无法识别新安装技能。

### 2\.3 安装验证方法

- 可视化验证：打开 WorkBuddy 左侧「技能/技能市场」入口，查看是否已加载 OTP 靶标评估技能

- 目录验证：检查对应路径下是否存在完整的`otp-target-assessment` 技能目录及核心文件

## 三、分发包内容说明

本次打包文件已通过 WorkBuddy 官方工具校验，执行 `package_skill.py` 输出 `Skill is valid`，为合规可用的标准技能包。

### 包内完整资源清单

- 核心配置：`SKILL.md`（技能规则、触发逻辑、执行流程定义）

- 功能脚本（3个）：OTP 批量查询脚本、PDB 靶点核实脚本、文献标题提取脚本

- 参考文档（2份）：标准化查询模板\&常见避坑指南、OTP靶标评估五步法框架

- 资源模板（1份）：标准化中文HTML评估报告骨架

### 环境依赖说明

所有脚本仅使用 **Python 标准库**，无第三方依赖，安装后无需联网下载依赖包，在任意预装 WorkBuddy 的设备上均可直接运行。

## 四、团队分享方式

如需分享给同事/团队成员，直接分发仓库中 `otp-target-assessment.zip` 压缩包，并指引对方按照本文档 **第二章节（分发包安装指南）** 完成部署即可。

> （注：部分内容由 Workbuddy/DeepSeek-V4-Flash 辅助生成、排版）
