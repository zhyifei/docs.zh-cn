---
ms.openlocfilehash: 99153bb9cf3287951a1e52e716c799ee64eb82ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78950992"
---
# <a name="labels-and-projects-roadmap"></a>标签和项目路线图

.NET 文档团队广泛使用 [GitHub 标签](https://github.com/dotnet/docs/labels)来组织我们的工作。 通过按标签组合进行筛选，我们可以在 [.NET 文档网站](https://docs.microsoft.com/dotnet)中迅速找到所感兴趣的部分。

此外，我们还使用 [GitHub 项目](https://github.com/dotnet/docs/projects)组织冲刺和其他实现目标的长篇故事。

此路线图说明了我们使用这些组织工具的方式，并提供了用于查找感兴趣内容的便捷筛选器的链接。

## <a name="labels"></a>标签

如果这你是首次体验参与 [dotnet/docs](https://github.com/dotnet/docs)，请从[容易作答](https://github.com/dotnet/docs/labels/up-for-grabs)的问题开始。 这些问题针对的范围更加集中。 从此类问题入手是完成首次参与的好方式。 从“容易作答”视图中，你可以进一步根据区域和优先级筛选问题。 我们已使用 [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) 标签标识出适合新手回答的问题，以便于你完成首次小小的参与。

我们使用标签以多种不同方式来分类问题：

- [.NET 指南](#find-a-single-net-guide)和[指南章节](#search-one-section-of-a-guide)。
- [目标版本](#releases)
- [Priority](#priority)

你可以合并每组（指南、版本、优先级）中的标签，以缩小关注范围，查找你想要解决的问题。

### <a name="find-a-single-net-guide"></a>查找单个 .NET 指南

我们针对各个体系结构电子书以及各个 .NET 指南使用标签。

![:book: guide on light green background](./images/guide.png "体系结构指南标签的前缀")

体系结构电子书标有 `:book: guide` 前缀，并且使用浅绿色背景。 这些是长格式区域，其中包含推荐的体系结构。 以下是针对各个 .NET 体系结构指南筛选出的当前问题。

- [ASP.NET Core Web 应用](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [Blazor](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [云原生](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [Docker 生命周期](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [gRPC](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [通过 Windows 容器实现现代化](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [.NET 微服务](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [无服务器应用](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

此标签样式也适用于 [Framework 设计准则](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines)。 此区域使用相同的标签设计，但不建议对它执行社区拉取请求。 此为经许可后转载的材料，请勿进行编辑。

![:books:Area on dark blue background](./images/area.png ".NET 指南区域标签的前缀")

每个 .NET 指南都标有 `:books: Area` 前缀，并且使用深蓝色背景。 以下是针对各个 .NET 指南筛选出的当前问题。

- [API 参考](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [Azure .NET SDK](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [C# 指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [桌面指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [F# 指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [ML.NET 指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- [.NET 体系结构指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - 可以删除
- [.NET Core 指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [.NET for Apache Spark 指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [.NET Framework 指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [.NET 指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- [Roslyn API 参考](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - 可以删除。
- [Visual Basic 指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a>搜索指南的某个章节

![:card_file_box:Area on medium blue background](./images/technology.png ".NET 指南子区域标签的前缀")

.NET 指南范围较大，因此，这些标签按指南章节对范围做了进一步限制。 每个 .NET 指南的子区域都标有 `:card_file_box: Technology` 前缀，并且使用中蓝色背景。 其中许多标签适用于多个指南，而有些标签仅适用于一个指南。 基于区域筛选后，添加其中一种标签，进一步限制问题的范围。

- AppCompat
- 异步任务
- C# 高级概念
- C# 编译器
- C# 基础知识
- C# 入门
- C# 语言参考
- C# Null 安全性
- C# 新增功能
- CLI
- 数据访问
- Docker
- 安装程序
- LINQ
- NCL
- .NET Standard
- Roslyn API
- 安全性
- WCF
- WF
- WIF
- WinForms
- WPF

### <a name="releases"></a>发布

![:checkered_flag:Release: on dark yellow](./images/release.png "版本标签的前缀")

针对特定版本标记的问题标有 `:checkered_flag: Release:` 前缀，并且使用深黄色背景。

- .NET Core 2.2
- .NET Core 3.0

### <a name="priority"></a>Priority

优先级标签由 `P` 及其后面的单个数字构成。 数字越小表示优先级越高：

- P0
- P1
- P2

### <a name="what-about-the-other-labels"></a>其他还有哪些标签？

内容团队还使用了许多其他标签来管理各种问题分类。 如果你不属于内容团队，则可以忽略其他这些标签。

## <a name="projects"></a>项目

参与者应查看[适用于 .NET 社区协作者的项目](https://github.com/dotnet/docs/projects/35)。 我们已针对维护、文档更新和新内容任务创建了不同的列。 这也是一种查找感兴趣任务的方法。 （请注意，可以使用上述标签筛选项目视图。）

此外，我们还通过其他两种方式使用项目：

- Month YYYY 项目类型：这些是每月工作计划的任务板。
- 长时间运行的长篇故事：当工作将在几个月内完成时，使用它们来组织实现目标的任务。
