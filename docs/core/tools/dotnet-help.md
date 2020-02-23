---
title: dotnet help 命令
description: dotnet help 命令可显示指定命令更详细的在线文档。
ms.date: 02/14/2020
ms.openlocfilehash: f5d9221ae18653451a3bf97dc82fae396ae4e288
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503729"
---
# <a name="dotnet-help-reference"></a>dotnet help 参考

 本文适用于： ✔️ .NET Core 2.0 SDK 及更高版本

## <a name="name"></a>“属性”

`dotnet help` - 显示指定命令更详细的在线文档。

## <a name="synopsis"></a>摘要

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>描述

`dotnet help` 命令打开 docs.microsoft.com 参考页，以提供指定命令的更多详细信息。

## <a name="arguments"></a>自变量

- **`COMMAND_NAME`**

  .NET Core CLI 命令名称。 有关有效 CLI 命令的列表，请参阅 [CLI 命令](index.md#cli-commands)。

## <a name="options"></a>选项

- **`-h|--help`**

  打印出有关命令的简短帮助。

## <a name="examples"></a>示例

- 打开 [dotnet new](dotnet-new.md) 命令的文档页：

  ```dotnetcli
  dotnet help new
  ```
