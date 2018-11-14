---
title: C# 中的新增功能 - C# 指南
description: C# 语言是如何不断发展的
ms.date: 11/13/2017
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: b079c21ee90a797b038b96ae68123a538464c382
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201434"
---
# <a name="whats-new-in-c"></a>C# 中的新增功能 #

本页介绍了 C# 语言每个主要版本中新增功能的路线图。 链接的文章详细介绍了每个版本中增加的主要功能。 可以在常规版本或公共预览版中找到有关已发布新功能的信息。 可以在 GitHub 上的 [dotnet/roslyn 存储库](https://github.com/dotnet/roslyn/blob/master/docs/Language%20Feature%20Status.md)上找到详细的语言功能状态，包括考虑在即将发布的版本中添加的功能。

> [!IMPORTANT]
> 为了提供一些功能，C# 语言依赖标准库中的类型和方法。 例如，异常处理。 为了确保引发的对象派生自 <xref:System.Exception>，将会检查每个 `throw` 语句或表达式。 同样，还会检查每个 `catch`，以确保捕获的类型派生自 <xref:System.Exception>。 每个版本都可能会新增要求。 若要在旧版环境中使用最新语言功能，可能需要安装特定库。 每个特定版本的页面中记录了这些依赖项。 若要了解此依赖项的背景信息，可以详细了解[语言与库的关系](relationships-between-language-and-library.md)。 

若要使用单点版本中的最新功能，需要[配置编译器语言版本](../language-reference/configure-language-version.md)并选择版本。

* [C# 7.3](csharp-7-3.md)：
  - 此页介绍了 C# 语言的最新功能。 C# 7.3 目前在 [Visual Studio 2017 版本 15.7](https://visualstudio.microsoft.com/vs/whatsnew/) 和 [.NET Core 2.1 SDK 2.1.300 RC1](../../core/whats-new/index.md) 中可用。
* [C# 7.2](csharp-7-2.md)：
  - 此页介绍 C# 语言中添加的功能。 C# 7.2 目前在 [Visual Studio 2017 版本 15.5](https://visualstudio.microsoft.com/vs/whatsnew/), 和 [.NET Core 2.0 SDK](../../core/whats-new/index.md) 中可用。
* [C# 7.1](csharp-7-1.md)：
  - 此页介绍 C# 7.1 中添加的功能。 [Visual Studio 2017 版本 15.3](https://visualstudio.microsoft.com/vs/whatsnew/), 和 [.NET Core 2.0 SDK](../../core/whats-new/index.md) 中增加了这些功能。
* [C# 7.0](csharp-7.md)：
  - 此页介绍 C# 7.0 中添加的功能。 [Visual Studio 2017](https://visualstudio.microsoft.com/vs/whatsnew/) 和 [.NET Core 1.0](../../core/whats-new/index.md) 及更高版本中增加了这些功能。
* [C# 6](csharp-6.md)：
  - 此页介绍 C# 6 中添加的功能。 这些功能可供 Windows 开发者在 Visual Studio 2015 中使用，并可供开发者在 macOS 和 Linux 上的 .NET Core 1.0 中探索 C# 时使用。
* [跨平台支持](../../core/index.md)：
  - 借助 .NET Core 支持，C# 可以在多个平台上运行。 如果希望在 macOS 或众多受支持的 Linux 发行版上使用 C#，请了解有关 .NET Core 的详细信息。
* [.NET 编译器平台 SDK](../roslyn-sdk/index.md)：
  - 借助 .NET 编译器平台 SDK，可以编写对 C# 代码执行静态分析的代码。 可以使用这些 API 来发现潜在错误或不正确的做法，以及建议并实现修补程序。

## <a name="previous-versions"></a>早期版本

下面列出了在以前版本的 C# 语言和 Visual Studio.NET 中引入的主要功能。

* Visual Studio .NET 2013：
  - 此版本的 Visual Studio 包含 .NET Compiler Platform（“Roslyn”）的 Bug 修复、性能改进和技术预览，Roslyn 是 [.NET Compiler Platform SDK](../roslyn-sdk/index.md) 的前身。
* C# 5，Visual Studio .NET 2012：
  - `Async` / `await` 和[调用方信息](../programming-guide/concepts/caller-information.md)特性。
* C# 4，Visual Studio .NET 2010：
  - `Dynamic`、[命名自变量](../programming-guide/classes-and-structs/named-and-optional-arguments.md)、可选参数、泛型[协变和逆变](../programming-guide/concepts/covariance-contravariance/index.md)。
* C# 3，Visual Studio .NET 2008：
  - 对象和集合初始值设定项、lambda 表达式、扩展方法、匿名类型、自动属性、本地 `var` 类型推理和[语言集成查询 (LINQ)](../programming-guide/concepts/linq/index.md)。
* C# 2，Visual Studio .NET 2005：
  - 匿名方法、泛型、可以为 null 的类型、迭代器/yield、`static` 类、委托的协变和逆变。
* C# 1.1，Visual Studio .NET 2003：
  - `#line` 杂注和 xml 文档注释。
* C# 1，Visual Studio .NET 2002：
  - [C#](../csharp.md) 初版。
