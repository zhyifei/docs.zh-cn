---
title: SourceLink 和 .NET 库
description: 有关使用 SourceLink 改进 .NET 库调试的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 3bc72e158a5773b656095f9ce58b442469f91e67
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128918"
---
# <a name="sourcelink"></a>SourceLink

SourceLink 是一种使开发人员可以从 NuGet 对 .NET 程序集进行源代码调试的技术。 SourceLink 在创建 NuGet 包时执行，然后将源代码管理元数据嵌入在程序集和包中。 下载包并且在 Visual Studio 中启用了 SourceLink 的开发人员可以单步执行其源代码。 SourceLink 提供源代码管理元数据来创造出色的调试体验。

## <a name="sourcelink-demo"></a>SourceLink 演示

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>使用 SourceLink

可以在 [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub 存储库上找到有关使用 SourceLink 的说明。

可以使用 [NuGet 包资源管理器](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)以确认 SourceLink 元数据是否已成功嵌入在包中。 检查 `Repository` 元数据是否存在并具有注释标识符，以及 .pdb 文件是否与每个目标的 .dll 放置在一起。

![NuGet 包资源管理器中的 SourceLink](./media/sourcelink/nuget-package-explorer-sourcelink.png "NuGet 包资源管理器中的 SourceLink")

✔️ 请考虑使用 SourceLink 将源代码管理元数据添加到程序集和 NuGet 包。

> [!TIP]
> 可以通过将调试器特性添加到类型来进一步增强开发人员的调试体验。
> * <xref:System.Diagnostics.DebuggerDisplayAttribute> 可以自定义类或字段在调试器变量窗口中的显示方式。
> * <xref:System.Diagnostics.DebuggerStepThroughAttribute> 指示调试器逐行执行代码，而不是单步执行代码。
> * <xref:System.Diagnostics.DebuggerBrowsableAttribute> 控制成员是否会显示在调试器变量窗口中以及其显示方式。

✔️ 请考虑将符号文件 (`*.pdb`) 包含在 NuGet 包中。

> 通常会在[符号包](./nuget.md#symbol-packages)中发布符号文件。 目前，符号包的主要公共主机不支持由 SDK 样式项目创建的可移植符号文件 (`*.pdb`)，并且符号包没有用处。

>[!div class="step-by-step"]
>[上一页](dependencies.md)
>[下一页](publish-nuget-package.md)