---
title: SourceLink 和.NET 库
description: 有关使用 SourceLink 提高调试.NET 库的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49369796"
---
# <a name="sourcelink"></a>SourceLink

SourceLink 是一种允许从 NuGet 由开发人员的.NET 程序集的源代码调试技术。 SourceLink 执行时创建 NuGet 包，然后将嵌入在程序集和包的源控件元数据。 下载包，并具有 SourceLink 在 Visual Studio 中启用开发人员可以单步执行它的源代码。 SourceLink 提供源控件元数据来创建出色的调试体验。

## <a name="sourcelink-demo"></a>SourceLink 演示

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>使用 SourceLink

可以上找到用于使用 SourceLink 说明[dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub 存储库。

可以使用[NuGet 包资源管理器](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)确认 SourceLink 元数据已成功嵌入包中。 检查`Repository`元数据是否存在具有注释标识符和.pdb 文件位于与每个目标的.dll。

![在 NuGet 包资源管理器的 SourceLink](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink 在 NuGet 包资源管理器")

**请考虑 ✔️**使用 SourceLink 将源控件元数据添加到你的程序集和 NuGet 包。

**请考虑 ✔️**包括 NuGet 包中的 PDB 文件。

>[!div class="step-by-step"]
[上一页](./dependencies.md)
[下一页](./publish-nuget-package.md)
