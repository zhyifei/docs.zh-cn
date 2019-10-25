---
title: 关于 .NET Core
description: 了解 .NET Core。
ms.date: 09/17/2019
ms.openlocfilehash: 8b96e1e8f882ee69bcf7db58ca7a5eeab89fb4fd
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395181"
---
# <a name="about-net-core"></a>关于 .NET Core

.NET Core 具有以下特性：

- **跨平台：** 可在 Windows、macOS 和 Linux [操作系统](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md)上运行。
- **跨体系结构保持一致：** 在多个体系结构（包括 x64、x86 和 ARM）上以相同的行为运行代码。
- **命令行工具：** 包括可用于本地开发和持续集成方案中的易于使用的命令行工具。
- **部署灵活：** 可以包含在应用或已安装的并行（用户或系统范围安装）中。 可搭配 [Docker 容器](docker/index.md)使用。
- **兼容性：** .NET Core 通过 [.NET Standard](../standard/net-standard.md) 与 .NET Framework、Xamarin 和 Mono 兼容。
- **开放源代码：** .NET Core 平台是开放源代码，使用 MIT 和 Apache 2 许可证。 .NET Core 是一个 [.NET Foundation](https://dotnetfoundation.org/) 项目。
- **由 Microsoft 支持：** .NET Core 由 Microsoft 依据 [.NET Core 支持](https://dotnet.microsoft.com/platform/support/policy)提供支持。

## <a name="languages"></a>语言

可以使用 C#、Visual Basic 和 F# 语言编写适用于 .NET Core 的应用程序和库。 这些语言可在你喜欢的文本编辑器或集成开发环境 (IDE) 中使用，包括：

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)
- Sublime Text
- Vim
 
这种集成部分由 [OmniSharp](https://www.omnisharp.net/) 和 [Ionide](http://ionide.io) 项目的参与者提供。

## <a name="apis"></a>API

.NET Core 公开了多种方案的 API，以下介绍了几种：

- 基元类型，例如 [bool](../csharp/language-reference/keywords/bool.md) 和 [int](../csharp/language-reference/builtin-types/integral-numeric-types.md)。
- 集合，例如 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 和 <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>。
- 实用程序类型，例如 <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 和 <xref:System.IO.FileStream?displayProperty=nameWithType>。
- 数据类型，例如 <xref:System.Data.DataSet?displayProperty=nameWithType> 和 [DbSet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/)。
- 高性能类型，例如 <xref:System.Numerics.Vector?displayProperty=nameWithType> 和 [Pipelines](https://devblogs.microsoft.com/dotnet/system-io-pipelines-high-performance-io-in-net/)。

.NET Core 通过实现 [.NET Standard](../standard/net-standard.md) 规范提供 .NET Framework 和 Mono API 的兼容性。

## <a name="frameworks"></a>框架

在 .NET Core 之上建立了多个框架：

- [ASP.NET Core](/aspnet/core/)
- [Windows 10 通用 Windows 平台 (UWP)](https://developer.microsoft.com/windows)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>撰写

.NET Core 包括以下部分：

- [.NET Core 运行时](https://github.com/dotnet/coreclr)：提供类型系统、程序集加载、垃圾回收器、本机互操作和其他基本服务。 [.NET Core 框架库](https://github.com/dotnet/corefx)：提供基元数据类型、应用编写类型和基本实用程序。
- [ASP.NET 运行时](https://github.com/aspnet/home)：提供一个框架来生成基于云且连接到 Internet 的新式应用程序，例如 Web 应用、IoT 应用和移动后端。
- [.NET Core CLI 工具](https://github.com/dotnet/cli)和语言编译器（[Roslyn](https://github.com/dotnet/roslyn) 和 [F#](https://github.com/microsoft/visualfsharp)）：提供 .NET Core 开发人员体验。
- [dotnet 工具](https://github.com/dotnet/core-setup)：用于启动 .NET Core 应用和 CLI 工具。 它选择运行时并托管运行时，提供程序集加载策略并启动应用和工具。

这些组件采用以下方式分布：

- [.NET Core 运行时](https://dotnet.microsoft.com/download) -- 包括 .NET Core 运行时和框架库。
- [ASP.NET Core 运行时](https://dotnet.microsoft.com/download) -- 包括 ASP.NET Core 和 .NET Core 运行时以及框架库。
- [.NET Core SDK](https://dotnet.microsoft.com/download) -- 包括 .NET CLI 工具、ASP.NET Core 运行时以及 .NET Core 运行时和框架。

### <a name="open-source"></a>开源

[.NET Core](https://github.com/dotnet/core) 是开源的（[MIT 许可证](https://github.com/dotnet/core/blob/master/LICENSE.TXT)），由 Microsoft 于 2014 年提供给 [.NET Foundation](https://dotnetfoundation.org)。 它现在是最活跃的 .NET Foundation 项目之一。 个人和公司可出于个人、学术或商业等目的对其进行使用。 许多公司将 .NET Core 用作应用、工具、新平台和托管服务的一部分。 其中某些公司在 GitHub 上为 .NET Core 做出了巨大贡献，并作为 [.NET Foundation Technical Steering Group](https://dotnetfoundation.org/blog/tsg-welcome)（.NET Foundation 技术控制组）的成员为产品方向提供指导。

### <a name="designed-for-adaptability"></a>针对适应性而设计

经过构建，.NET Core 与其他 .NET 产品非常相似，但也存在独特性。 它旨在实现对新平台和工作负荷广泛的适应性，还提供了多个 OS 和 CPU 端口（且可能会移植到更多端口上）。

该产品分为几个部分，使各个部件能够在不同的时间适应新的平台。 必须将运行时和特定于平台的基础库作为一个单元进行移植。 与平台无关的库应在所有平台上按照构建的原样运行。 在减少特定于平台的实现来提高开发人员效率方面存在项目偏差，但每当可以此方式全部或部分实现算法或 API 时，都应首选与平台无关的 C# 代码。

人们经常会问，为支持多个操作系统应如何实现 .NET Core。 他们还会问是否存在单独的实现，或是否使用 [conditional compilation](https://en.wikipedia.org/wiki/Conditional_compilation)（条件编译）。 这两者都在用，但强烈偏向条件编译。

可以在下面的图表看出大多数 [CoreFX](https://github.com/dotnet/corefx) 都是与平台无关的代码，该代码可在所有平台共享。 不限平台的代码可实现为在所有平台上使用的单个可移植程序集。

![CoreFX：每个平台的代码行数](../images/corefx-platforms-loc.png)

Windows 和 Unix 实现大小相似。 Windows 的实现范围更广，这是因为 CoreFX 会实现某些仅适用于 Windows 的功能（如 [Microsoft.Win32.Registry](https://github.com/dotnet/corefx/tree/master/src/Microsoft.Win32.Registry)），但尚未实现很多仅适用于 Unix 的概念。 你还将发现大多数 Linux 和 macOS 实现都跨 Unix 实现共享，而特定于 Linux 和 macOS 的实现大小大致相同。

.NET Core 中既存在平台特定的库，也存在与平台无关的库。 可以查看几个示例中的模式：

- [CoreCLR](https://github.com/dotnet/coreclr) 是特定于平台的。 它建立在内存管理器和线程计划程序等操作系统子系统的基础上。
- 考虑到每个 OS 上的存储和加密 API 都有所不同，[System.IO](https://github.com/dotnet/corefx/tree/master/src/System.IO) 和 [System.Security.Cryptography.Algorithms](https://github.com/dotnet/corefx/tree/master/src/System.Security.Cryptography.Algorithms) 是特定于平台的。
- 考虑到它们是通过数据结构创建和操作，[System.Collections](https://github.com/dotnet/corefx/tree/master/src/System.Collections) 和 [System.Linq](https://github.com/dotnet/corefx/tree/master/src/System.Linq) 是与平台无关的。

## <a name="comparisons-to-other-net-implementations"></a>与其他 .NET 实现比较

通过将 .NET Core 与现有的 .NET 实现进行比较，可能更容易了解其大小和形状。

### <a name="comparison-with-net-framework"></a>与 .NET Framework 比较

.NET 由 Microsoft 于 2000 年首次发布，而后发展至今。 近 20 年以来，.NET Framework 一直是 Microsoft 出品的主要 .NET 实现。

.NET Core 和 .NET Framework 的主要差异在于：

- **应用模型** - .NET Core 并非支持全部 .NET Framework 应用模型。 具体而言，它不支持 ASP.NET Web 窗体和 ASP.NET MVC，但支持 ASP.NET Core MVC。 自 .NET Core 3.0 起，.NET Core 还支持 WPF 和 Windows 窗体（仅限在 Windows 上）。
- **API** -- .NET Core 包含 .NET Framework 基类库的一个大型子集，但具有不同的组成要素（程序集名称不同；类型上公开的成员在关键用例中不同）。 在某些情况下，这些差异要求进行更改，以将源移植到 .NET Core 中。 有关详细信息，请参阅 [.NET 可移植性分析器](../standard/analyzers/portability-analyzer.md)。 .NET Core 实施 [.NET Standard](../standard/net-standard.md) API 规范。
- **子系统** -- .NET Core 实现 .NET Framework 中子系统的子级，目的是实现更简单的实现和编程模型。 例如，不支持代码访问安全性 (CAS)，但支持反射。
- **平台** -- .NET Framework 支持 Windows 和 Windows Server，而 NET Core 还支持 macOS 和 Linux。
- **开源** -- .NET Core 是开源的，而 [.NET Framework 的只读子集](https://github.com/microsoft/referencesource)是开源的。

虽然 .NET Core 是唯一的且与 .NET Framework 和其他 .NET 实现大不相同，但可使用源或二进制共享技术在这些实现之间轻松共享代码。

由于 .NET Core 支持并行安装及其运行时完全独立于 .NET Framework，它可以安装在装有.NET Framework 的计算机上，不会出现任何问题。

### <a name="comparison-with-mono"></a>与 Mono 比较

[Mono](https://www.mono-project.com/) 是 .NET 的原始跨平台。 它一开始是用作 .NET Framework 的[开放源代码](https://github.com/mono/mono)替代项，之后随着 iOS 和 Android 设备变得流行，过渡到面向移动设备。 可将它看作是 .NET Framework 的社区克隆。 Mono 项目团队依赖于 Microsoft 发布的开放 [.NET 标准](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md)（尤其是 ECMA 335）来实现兼容性。

.NET Core 和 Mono 的主要差异在于：

- **应用模型** - Mono 通过 Xamarin 产品支持部分 .NET Framework 应用模型（例如 Windows 窗体）和其他移动开发辅助模型（例如 [Xamarin.iOS](https://www.xamarin.com/platform)）。 而 .NET Core 不支持 Xamarin。
- **API** -- Mono 使用相同程序集名称和组成要素支持 .NET Framework API 的 [大型子集](http://docs.go-mono.com/?link=root%3a%2fclasslib)。
- **平台** -- Mono 支持很多平台和 CPU。
- **开源** -- Mono 和 .NET Core 两者都使用 MIT 许可证，且都属于 .NET Foundation 项目。
- **焦点** -- 最近几年，Mono 的主要焦点是移动平台，而 .NET Core 的焦点是云和桌面工作负载。

## <a name="the-future"></a>未来动向

已宣布 .NET 5 将成为 .NET Core 的下一版本且表示平台实现统一。 此项目旨在以几项关键方法来改进 .NET：

- 生成可随处使用且提供统一运行时行为和开发人员体验的单一 .NET 运行时和框架。
- 通过充分利用 .NET Core、.NET Framework、Xamarin 和 Mono 来扩展 .NET 的功能。
- 根据单个基本代码构建开发人员（Microsoft 和社区）可处理且协同扩展，同时可改善所有方案的产品。

要详细了解当前规划的 .NET 5 发展动向，请参阅 [.NET 5 简介](https://devblogs.microsoft.com/dotnet/introducing-net-5/)。
