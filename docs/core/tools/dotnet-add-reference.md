---
title: dotnet add reference 命令
description: dotnet add reference 命令可便于添加项目间引用。
ms.date: 02/14/2020
ms.openlocfilehash: 84ea25e94efc8d84aebfeccf62c30a64551c5019
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503789"
---
# <a name="dotnet-add-reference"></a>dotnet add reference

**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>名称

`dotnet add reference` - 添加项目到项目 (P2P) 引用。

## <a name="synopsis"></a>摘要

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a>说明

使用 `dotnet add reference` 命令可方便地向项目添加项目引用。 运行该命令后，会将 `<ProjectReference>` 元素添加到项目文件。

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>参数

- **`PROJECT`**

  指定项目文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。

- **`PROJECT_REFERENCES`**

  要添加的项目到项目 (P2P) 引用。 指定一个或多个项目。 基于 Unix/Linux 的系统支持 [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。

## <a name="options"></a>选项

- **`-h|--help`**

  打印出有关命令的简短帮助。

- **`-f|--framework <FRAMEWORK>`**

  仅在以特定[框架](../../standard/frameworks.md)为目标时添加项目引用。

- **`--interactive`**

  允许命令停止并等待用户输入或操作（例如，完成身份验证）。 自 .NET Core 3.0 SDK 起可用。

## <a name="examples"></a>示例

- 添加项目引用：

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- 向当前目录中的项目添加多个项目引用：

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- 使用 glob 模式在 Linux/Unix 上添加多个项目引用：

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
