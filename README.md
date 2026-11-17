# 求职助手（桌面包）

本地运行的求职效率工具桌面包装版。按你设定的城市、岗位、薪资等条件，在 Boss 直聘、猎聘、51job、智联招聘筛选岗位，并用你写好的招呼语发送第一条消息。可选的 AI 招呼语只对 Boss 直聘生效，默认关闭，不填密钥也能完整使用。

**本项目按免费、非商业方式分享。** 不收取软件费用，文档中也不提供购买入口。

仓库：https://github.com/zac-wtf/get-jobs-desktop  
问题反馈：https://github.com/zac-wtf/get-jobs-desktop/issues  
Release：https://github.com/zac-wtf/get-jobs-desktop/releases

当前包版本：`2.0.1`（macOS 应用 `CFBundleShortVersionString` / jar 内 `build.version`）。  
jar 构建时间：`2026-11-11T08:54:42Z`（合 2026-11-11 00:54，America/Los_Angeles）。

本文档依据已构建的安装包、使用说明和公开上游资料整理，不包含未公开的构建源码或从源码编译的步骤，也未编造未在材料中出现的功能。

## 本仓库包含什么（重要）

这是一个**说明文档与安装包的分发仓库**，不是完整的桌面构建源码仓库。

- 这里提供使用说明和许可证。Windows / macOS 安装包计划通过 GitHub Releases 提供。
- 本仓库**不包含**桌面包的打包源码或构建脚本，因此也不能提供「如何从源码重新编译这一桌面包」的步骤。
- 核心程序来自上游开源项目 [get_jobs](https://github.com/loks666/get_jobs)。若你要阅读或修改核心实现，请前往上游仓库。

## 如何获取安装包

公开候选安装包的文件名是 `求职助手-Windows-公开候选.zip` 和 `求职助手-macOS-公开候选.zip`，校验和见 [安装包校验.txt](./安装包校验.txt) 与 [SHA256SUMS](./SHA256SUMS)。

**当前还不能下载。** Release `v2.0.1` 在附件上传完成前没有可下载的安装包，请不要把本仓库或 Release 页当作已经可以取得安装文件的地方。

## 和上游项目的关系

本桌面包的核心程序来自开源项目 [get_jobs](https://github.com/loks666/get_jobs)（Gitee：[lok666/get_jobs](https://gitee.com/lok666/get_jobs)）。jar 元数据中的构件名为 `get_jobs`，组织为 `com.getjobs`，应用配置里的项目说明也指向上述仓库。

本包装的目标，是让不熟悉 Java / Node / Gradle 的使用者解压后即可启动：包内已带 JRE 21、Node 运行时和浏览器驱动，用本地管理页和启动脚本代替自行搭环境。

## 许可证与署名

截至 2026-11-17（America/Los_Angeles）从上游仓库核对到的许可证是 **PolyForm Noncommercial License 1.0.0**。当前这次发布按该许可证做**免费非商业分发**。

- 本仓库中的 [LICENSE](./LICENSE)
- 许可证原文：https://github.com/loks666/get_jobs/blob/main/LICENSE
- 上游 README：https://github.com/loks666/get_jobs/blob/main/README.md
- 安装包内同样附带 `LICENSE.txt` 与 `NOTICE.txt`

分发时必须向接收方提供协议条款或条款 URL，以及原文中以 `Required Notice:` 开头的声明：

> Required Notice: Copyright (c) 2024-2026 GET JOBS (https://github.com/loks666/get_jobs)

上游 LICENSE 在正式条款之后还有一份**不属于协议正文、也不修改正文**的说明：售卖本软件或其修改版本、以其提供收费服务、将其整合进商业产品或对外收费平台等，属于商业用途，需另行取得书面授权。该说明同时记载：2025-11-11 之前的版本曾以 MIT 发布，该日之前已发布版本的授权不可撤销，之后版本适用本协议。当前桌面包为 2.0.1，构建于 2026-11-11，应按变更后的许可证理解。

**若将来改为收费或其他商业使用，需要再单独核对并取得相应授权。那不是当前这次免费分享的前提。**

## 能做什么

依据包内《使用说明》和程序配置，当前桌面包提供：

- 在你自己的电脑上运行，管理页地址为 `http://127.0.0.1:9527`（有时也会打开 `http://127.0.0.1:6866`，是同一页面）
- 同一界面覆盖 Boss 直聘、猎聘、51job、智联招聘；各平台筛选条件相互独立，需分别修改并保存
- 按城市、关键词、薪资等条件筛选，使用你填写的招呼语发送第一条消息
- 可选：为 Boss 直聘根据职位描述生成招呼语，或在不匹配时跳过；需你自己提供兼容 OpenAI 格式的接口地址和密钥，费用由你向该服务商支付，与本桌面包的免费分享无关；失败时会退回固定招呼语
- 黑名单、过滤不活跃 HR、投递记录等能力（具体选项以管理页为准）
- 在自动弹出的 Chrome 窗口中扫码登录；登录态保存在本机，工具不要求你填写招聘网站密码
- 数据与程序分离：重装软件本体不会覆盖数据目录

它只协助筛岗和发出第一条招呼，不代为面试、不代管账号、也不承诺求职结果。请自行控制使用频率，并遵守各招聘平台的服务条款。

## 运行环境

| 项目 | 要求 |
|---|---|
| Windows | 64 位 Windows 10 或 Windows 11 |
| macOS | macOS 11 或更高，且为 Apple 芯片（M1 / M2 / M3 / M4） |
| 浏览器 | 必须已安装 Google Chrome |
| 磁盘 | 预留约 500–600 MB |
| 开发环境 | **不需要**自行安装 Java、Node.js 或数据库 |

当前包不支持 Intel 芯片的 Mac（包内 Node 与 JRE 为 arm64）。Windows ARM（如骁龙本）未作为支持范围写进说明。

按维护者说明，Windows 与 macOS 包均已在其环境中验证通过；整理本文档时未再次亲自复测启动流程。

## 如何运行

见 [安装指南.md](./安装指南.md)。简要步骤：解压整个压缩包到本地磁盘，Windows 双击 `启动求职助手.vbs`，macOS 对 `求职助手.app` 使用右键「打开」。然后在自动弹出的 Chrome 窗口中扫码，并在管理页把四个平台的条件改成你自己的，再开始。

请先确认你已从本仓库 Release 中下载到带附件的安装包。**在附件上传完成前，这里还不能下载。**

## 数据存放位置

- Windows：`%LOCALAPPDATA%\GetJobs`（即 `C:\Users\你的用户名\AppData\Local\GetJobs`）
- macOS：`~/Library/Application Support/GetJobs`

目录中通常包含数据库、浏览器登录态和日志。换电脑时拷贝整个数据目录即可继续使用。关闭管理页浏览器标签并不会停止后台程序。

## 使用前请注意

- 软件未经付费代码签名。Windows 可能出现 SmartScreen「已保护你的电脑」，macOS 可能提示无法验证开发者。这是签名状态造成的，说明里写了如何继续打开，但不等于已经过平台公证。
- 管理页第一屏是「环境变量配置」（接口地址、API Key、模型名）。这三项只服务于可选的 AI 招呼语，**不用 AI 就不必填**。
- 出厂默认筛选条件来自 jar 内模板，使用说明记载为「上海 + 大模型/Java/Python/Go + 5-10年经验」。只改其中一个平台、却点了其他平台的「开始投递」，会按该平台仍保存的默认条件去投。
- jar 内默认配置还带有模板黑名单，以及非空的默认招呼语 / AI 介绍与提示词。当前分发的安装包不修改这些默认值。
- 公开候选安装包已附带 `LICENSE.txt` 与 `NOTICE.txt`。包内说明指向本项目 Issues；若你使用的安装包仍写着「地址待填」，请以本仓库的 Issues 页面为准：https://github.com/zac-wtf/get-jobs-desktop/issues

## 文档

- [安装指南.md](./安装指南.md)
- [发布说明.md](./发布说明.md)
- [许可证与署名说明.md](./许可证与署名说明.md)
- [NOTICE](./NOTICE)
- [安装包校验.txt](./安装包校验.txt)
