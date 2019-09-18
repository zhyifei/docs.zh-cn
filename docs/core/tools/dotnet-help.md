---
title: dotnet help 命令
description: dotnet help 命令可显示指定命令更详细的在线文档。
ms.date: 08/08/2019
ms.openlocfilehash: e76f858f2529afc50646473f1aab9d52730cff16
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990463"
---
# <a name="dotnet-help-reference"></a>dotnet help 参考

**本文适用于：✓** .NET Core 2.0 SDK 及更高版本

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a>name

`dotnet help` - 显示指定命令更详细的在线文档。

## <a name="synopsis"></a>摘要

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>说明

`dotnet help` 命令打开 docs.microsoft.com 参考页，以提供指定命令的更多详细信息。

## <a name="arguments"></a>自变量

* **`COMMAND_NAME`**

  .NET Core CLI 命令名称。 有关有效 CLI 命令的列表，请参阅 [CLI 命令](index.md#cli-commands)。

## <a name="options"></a>选项

* **`-h|--help`**

  打印出有关命令的简短帮助。

## <a name="examples"></a>示例

* 打开 [dotnet new](dotnet-new.md) 命令的文档页：

  ```console
  dotnet help new
  ```
