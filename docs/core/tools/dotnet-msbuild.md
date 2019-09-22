---
title: dotnet msbuild 命令
description: dotnet msbuild 命令可提供对 MSBuild 命令行的访问权限。
ms.date: 12/03/2018
ms.openlocfilehash: b83f1272cdd4c5fcdb6b1e34aef7692e9acc01cd
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117701"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet msbuild` - 生成项目及其所有依赖项。

## <a name="synopsis"></a>摘要

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>说明

`dotnet msbuild` 命令允许访问功能完备的 MSBuild。

该命令与仅适用于 SDK 样式项目的现有 MSBuild 命令行客户端具有完全相同的功能。 选项一致。 有关可用选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。

[dotnet build](dotnet-build.md) 命令相当于 `dotnet msbuild -restore -target:Build`。 `dotnet build` 更常用于生成项目，但 `dotnet msbuild` 可使用户更好地进行控制。 例如，如果想要运行特定目标（而不运行生成目标），可能更倾向于使用 `dotnet msbuild`。

## <a name="examples"></a>示例

* 生成项目及其依赖项：

  ```dotnetcli
  dotnet msbuild
  ```

* 使用“发布”配置生成项目及其依赖项：

  ```dotnetcli
  dotnet msbuild -p:Configuration=Release
  ```

* 运行发布目标并发布 `osx.10.11-x64` RID：

  ```dotnetcli
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* 请参阅包含 SDK 添加的所有目标的整个项目：

  ```dotnetcli
  dotnet msbuild -pp
  ```
