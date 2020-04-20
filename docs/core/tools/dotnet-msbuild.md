---
title: dotnet msbuild 命令
description: dotnet msbuild 命令可提供对 MSBuild 命令行的访问权限。
ms.date: 02/14/2020
ms.openlocfilehash: 88e85868e2d7de564b2e4c90ce6e78bde4cb350e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463628"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本

## <a name="name"></a>名称

`dotnet msbuild` - 生成项目及其所有依赖项。

## <a name="synopsis"></a>摘要

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a>说明

`dotnet msbuild` 命令允许访问功能完备的 MSBuild。

该命令与仅适用于 SDK 样式项目的现有 MSBuild 命令行客户端具有完全相同的功能。 选项一致。 有关可用选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。

[dotnet build](dotnet-build.md) 命令相当于 `dotnet msbuild -restore -target:Build`。 [dotnet build](dotnet-build.md) 更常用于生成项目，但由于它始终运行生成目标，因此不想生成项目时可以使用 `dotnet msbuild`。 例如，如果想要运行特定目标而不生成项目，请使用 `dotnet msbuild` 指定目标。

## <a name="examples"></a>示例

- 生成项目及其依赖项：

  ```dotnetcli
  dotnet msbuild
  ```

- 使用“发布”配置生成项目及其依赖项：

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- 运行发布目标并发布 `osx.10.11-x64` RID：

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- 请参阅包含 SDK 添加的所有目标的整个项目：

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
