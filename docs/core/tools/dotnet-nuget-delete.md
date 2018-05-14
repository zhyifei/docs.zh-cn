---
title: dotnet nuget delete 命令 - .NET Core CLI
description: dotnet-nuget-delete 命令从服务器删除或取消列出包。
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 639ade54bfed5eb2de89bdb3b7f451393b4be187
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet nuget delete` - 从服务器删除或取消列出包。

## <a name="synopsis"></a>摘要

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a>描述

`dotnet nuget delete` 命令从服务器删除或取消列出包。 对于 [NuGet.org](https://www.nuget.org/)，该操作将取消列出包。

## <a name="arguments"></a>自变量

`PACKAGE_NAME`

要删除的包。

`PACKAGE_VERSION`

要删除的包的版本。

## <a name="options"></a>选项

`-h|--help`

打印出有关命令的简短帮助。

`-s|--source <SOURCE>`

指定服务器 URL。 Nuget.org 的支持 URL 包括 `http://www.nuget.org`、`http://www.nuget.org/api/v3` 和 `http://www.nuget.org/api/v2/package`。 对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。

`--non-interactive`

不提示用户输入或确认。

`-k|--api-key <API_KEY>`

服务器的 API 密钥。

`--force-english-output`

强制命令行输出以英语显示。

## <a name="examples"></a>示例

删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版：

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版（不提示用户需要凭据或其他输入）：

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`