---
title: WPF 社区反馈
ms.date: 03/01/2018
helpviewer_keywords:
- community resources [WPF]
- forums [WPF]
- bug descriptions [WPF]
ms.assetid: 468b060a-d54b-4900-a74a-9faccb554045
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6394bda1c2bcd4a42f76579d541173e65ecd2dc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557831"
---
# <a name="wpf-community-feedback"></a>WPF 社区反馈

Microsoft 公开各种社区资源以便于你了解、 讨论，并提供在 Windows Presentation Foundation (WPF) 的反馈。 这些资源包括论坛和[Visual Studio 开发人员社区](https://developercommunity.visualstudio.com/)站点。 每种社区资源的优点各不相同。 是使用每个以确保最佳响应来自社区和 Microsoft 特别的最佳实践的一组将在这里，介绍这些优点。

> [!NOTE]
> 不要使用位于每个页的底部的反馈部分来发送产品反馈。 这些链接仅用于发送文档反馈。

## <a name="forums"></a>论坛

[WPF 论坛](https://social.msdn.microsoft.com/Forums/vstudio/en-US/home?forum=wpf)是用于讨论和解决问题的主社区资源。 论坛通过提供一整套支持功能来便于讨论和解决问题，其中包括：

- 搜索。
- 讨论跟踪。
- 丰富的文本和代码格式。
- Visual Studio 集成。
- 最具价值专家 (MVP) 和社区参与。
- 确保以最快速度响应文章的监视功能。

为你要询问有关 WPF 社区的问题的另一个选项是[堆栈溢出](https://stackoverflow.com/questions/tagged/wpf)。

### <a name="forum-best-practices"></a>论坛最佳做法

使用以下最佳实践来解决问题最快可能及时发布到 WPF 论坛的帮助。 这些做法适用于所有论坛。

#### <a name="search-existing-posts"></a>搜索现有的文章

某些问题普遍存在，在你之前，其他人已经遇到过这些问题。 因此，你可以快速解决问题，也可以在现有讨论中添加意见。

#### <a name="use-meaningful-titles"></a>使用有意义的标题

简洁而有意义的标题提高您的发布的可发现性。 它们还便于其他 WPF 论坛社区成员，以确定是否能够解决你的问题。

#### <a name="include-appropriate-content"></a>包括合适的内容

描述了此问题和如何你尝试通过其工作。 如有可能，请包含支持的代码段或可能的最简单示例以演示问题。 所有这些详细信息都将有助于增加快速解答问题的机会。

## <a name="visual-studio-developer-community"></a>Visual Studio 开发人员社区

有时，问题可能会难以解决或无法解决。 出现这些情况是因为技术中有 Bug、将技术应用到特定方案存在困难或缺少对特定方案的支持。 此信息对 Microsoft 非常重要，且可以通过提供[Visual Studio 开发人员社区](https://developercommunity.visualstudio.com/)站点。

在 WPF 产品反馈中心上发布的项将被路由到 WPF 团队内部的 bug 数据库。 因此，并获取你的反馈到 WPF 功能所有者的最可靠方法。 此外，你可以验证和跟踪的建议和 bug，以及对它们投票，从而可帮助 WPF 团队，以确定问题的优先级。

### <a name="developer-community-best-practices"></a>开发人员社区最佳做法

当发布到 Visual Studio 开发人员社区，搜索现有发送，提供有意义的标题和合适的内容是重要的最佳做法，就像它们为发布到 WPF 论坛。 下面列出了一些还应使用的其他最佳做法。

#### <a name="search-existing-posts"></a>搜索现有的文章

某些问题普遍存在，在你之前，其他人已经遇到过这些问题。 因此，你可以快速解决问题，也可以添加你现有问题的输入。

#### <a name="use-meaningful-titles"></a>使用有意义的标题

简洁而有意义的标题可增加在最短时间内的定向到最适当的 WPF 团队包含你的问题的可能性。 这是对于 WPF，其中包含许多相关的功能等技术尤为重要。

#### <a name="describe-how-to-reproduce-your-bug"></a>描述如何重现 bug

发布有关 Bug 的文章时，包含以下相关内容很重要：

- 提供清晰的 Bug 说明。
- 使用代码段支持 Bug 说明。
- 提供用于演示如何重现 Bug 的步骤列表。
- 包含有可能是用于重现 Bug 的最小代码示例。
- 指明 Bug 是否可以一成不变地重现。
- 包含相关的异常信息。

 如果 Bug 与安装或设置有关，请附加相关的安装日志和快照（位于 %temp% 文件夹中带有“dd_”前缀的文件）。

 对于编译或生成问题，请附加生成日志。 MSBuild 系统可以配置为支持具有多种详细级别的日志记录通过使用 /v： 从命令行开关或通过配置相应的级别从集成开发环境 (IDE) 等 Visual Studio。

#### <a name="provide-environment-information"></a>提供环境信息

背景信息通常可用于向文章添加上下文。 具体而言，提及的操作系统平台、 处理器系列和体系结构，如"Windows 10 版本 1709，intel （） 至强®，x64。"

如果所发布的问题与呈现相关，还应包含图形卡和驱动程序详细信息（如有可能）。 此信息非常重要，因为 WPF 是一个演示文稿框架。

#### <a name="provide-solution-or-project-information"></a>提供的解决方案或项目的信息

Bug 可能与用于开发和生成应用程序的工具以及生成的应用程序的类型有关。 因此，可以用于指定以下信息：

- 生成的应用程序的类型，如：
  - 应用程序 (*.exe*) 或库 (*.dll*)
  - 可扩展应用程序标记语言 (XAML) 浏览器应用程序 (XBAP)
  - 宽松型 XAML 应用程序
  - 安装的独立应用程序
  - 独立 ClickOnce 部署的应用程序
- 开发工具，如：
  - MSBuild
  - 表达式图形设计器
  - 表达式交互式设计器
  - Visual Studio
- 解决方案配置，如：
  - 一种解决方案
  - 单个项目
  - 具有多个依赖项目的解决方案
- 应用程序是否具有特定于语言或非特定于语言的资源。 例如，是否为 `Application`、`Page` 和 `Resource` 类型指定了 `UICulture` 项目属性或可本地化的元数据？
- 是否在 AssemblyInfo.cs 或 AssemblyInfo.vb 文件中使用了非特定于语言的设置。

#### <a name="provide-scenario-and-impact-information"></a>提供了方案和影响信息

提供有关显示 bug 及其影响的方案的信息。 它确定是否、 时，以及如何修复问题，或是否可以改用可接受的解决方法，此信息时对 WPF 团队非常重要。

通常，故障和数据丢失方案具有重大影响，因此也最容易确定优先级。 但是，某些 Bug 仅显示在不常见的方案中，在有些情况下这些方案也可能是主线方案。 提供围绕方案和影响的上下文可帮助 WPF 团队做出正确的决策。

## <a name="see-also"></a>请参阅

[如何报告 Visual Studio 2017 的问题](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)
