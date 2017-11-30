---
title: "dotnet-add reference 命令- .NET Core CLI"
description: "dotnet add reference 命令可便于添加项目间引用。"
author: mairaw
ms.author: mairaw
ms.date: 09/19/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 9c6b0f434a9d6b1431e375ec6a437497aaddfc61
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-add-reference"></a>dotnet-add reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>名称

`dotnet add reference` - 添加项目到项目 (P2P) 引用。

## <a name="synopsis"></a>摘要

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>描述

使用 `dotnet add reference` 命令可方便地向项目添加项目引用。 运行该命令后，会将 [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) 元素添加到项目文件。

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>参数

`PROJECT`

指定项目文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。

`PROJECT_REFERENCES`

要添加的项目到项目 (P2P) 引用。 指定一个或多个项目。 基于 Unix/Linux 的系统支持 [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。

## <a name="options"></a>选项

`-h|--help`

打印出有关命令的简短帮助。

`-f|--framework <FRAMEWORK>`

仅在以特定[框架](../../standard/frameworks.md)为目标时添加项目引用。

## <a name="examples"></a>示例

添加项目引用：

`dotnet add app/app.csproj reference lib/lib.csproj`

在当前目录中添加对项目的多个项目引用：

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

使用 glob 模式在 Linux/Unix 上添加多个项目引用：

`dotnet add app/app.csproj reference **/*.csproj`
