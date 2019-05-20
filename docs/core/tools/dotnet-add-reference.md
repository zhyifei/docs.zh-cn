---
title: dotnet-add reference 命令
description: dotnet add reference 命令可便于添加项目间引用。
ms.date: 04/24/2019
ms.openlocfilehash: e90f95527d4f14c7851ccd8d30201daaaaefa2ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631943"
---
# <a name="dotnet-add-reference"></a>dotnet-add reference

**本文适用于：✓** .NET Core 1.x SDK 及更高版本

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet add reference` - 添加项目到项目 (P2P) 引用。

## <a name="synopsis"></a>摘要

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>说明

使用 `dotnet add reference` 命令可方便地向项目添加项目引用。 运行该命令后，会将 [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) 元素添加到项目文件。

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>自变量

* **`PROJECT`**

  指定项目文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。

* **`PROJECT_REFERENCES`**

  要添加的项目到项目 (P2P) 引用。 指定一个或多个项目。 基于 Unix/Linux 的系统支持 [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。

## <a name="options"></a>选项

* **`-h|--help`**

  打印出有关命令的简短帮助。

* **`-f|--framework <FRAMEWORK>`**

  仅在以特定[框架](../../standard/frameworks.md)为目标时添加项目引用。

## <a name="examples"></a>示例

* 添加项目引用：

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* 向当前目录中的项目添加多个项目引用：

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* 使用 glob 模式在 Linux/Unix 上添加多个项目引用：

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```
