---
title: dotnet help 命令 - .NET Core CLI
description: dotnet help 命令可显示指定命令更详细的在线文档。
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: ed152717e32ffb294f5d5bd8e5eb74d55e33e506
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696593"
---
# <a name="dotnet-help-reference"></a>dotnet help 参考

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>name

`dotnet help` - 显示指定命令更详细的在线文档。

## <a name="synopsis"></a>摘要

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>描述

`dotnet help` 命令打开 docs.microsoft.com 参考页，以提供指定命令的更多详细信息。

## <a name="arguments"></a>自变量

`COMMAND_NAME`

.NET Core CLI 命令名称。 有关有效 CLI 命令的列表，请参阅 [CLI 命令](index.md#cli-commands)。

## <a name="options"></a>选项

`-h|--help`

打印出有关命令的简短帮助。

## <a name="examples"></a>示例

打开 [dotnet new](dotnet-new.md) 命令的文档页：

`dotnet help new`
