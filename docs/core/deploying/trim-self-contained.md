---
title: 剪裁独立应用程序
description: 了解如何剪裁独立应用以减小其大小。 .NET Core 将运行时与独立发布的应用捆绑在一起，通常包含比所需更多的运行时。
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665619"
---
# <a name="trim-self-contained-deployments-and-executables"></a>剪裁独立部署和可执行文件

当发布独立应用程序时，.NET Core 运行时会与该应用程序捆绑在一起。 此捆绑包向打包的应用程序添加了大量内容。

在涉及到应用程序部署时，大小通常是一个重要因素。 使包应用程序的大小尽可能小通常是应用程序开发者的目标。

根据应用程序的复杂性，运行应用程序只需要运行时的子集。 不需要这些未使用的运行时部分，可以从打包的应用程序中进行剪裁。

> [!NOTE]
> 剪裁是 .NET Core 3.1 中的实验性功能，只能用于独立发布的应用程序  。

## <a name="trim-your-application"></a>剪裁应用程序

下面的示例演示如何使用 [dotnet publish](../tools/dotnet-publish.md) 命令剪裁应用程序：

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

剪裁功能的工作方式是检查应用程序二进制文件，以发现和生成所需运行时程序集的关系图。 未引用的其余运行时程序集会被剪裁。

## <a name="trimming-issues-when-using-reflection"></a>使用反射时的剪裁问题

在某些情况下，剪裁功能无法检测到引用。 例如，使用反射的应用程序可能会遇到此问题，因为只有在运行时才知道程序集的依赖项。

仅当反射使用依赖于未直接引用的运行时程序集时，剪裁才会成为问题。 请记住，应用程序代码可能未直接使用反射，但是所引用的第三方程序集可能在使用反射。

当代码通过反射引用某个 API，而你不希望链接器剪裁包含该 API 的程序集时，可以修改项目文件以从剪裁过程中排除该程序集。 下面的示例演示如何防止剪裁名为 `System.Security` 的程序集：

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a>请参阅

- [.NET Core 应用程序部署](index.md)
