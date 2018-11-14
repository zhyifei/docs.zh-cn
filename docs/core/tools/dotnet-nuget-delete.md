---
title: dotnet nuget delete 命令 - .NET Core CLI
description: dotnet-nuget-delete 命令从服务器删除或取消列出包。
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: f4aa027a465c4adea1de13853063d03e8e295411
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180871"
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet nuget delete` - 从服务器删除或取消列出包。

## <a name="synopsis"></a>摘要

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a>描述

`dotnet nuget delete` 命令从服务器删除或取消列出包。 对于 [NuGet.org](https://www.nuget.org/)，该操作将取消列出包。

## <a name="arguments"></a>自变量

`PACKAGE_NAME`

要删除的包的名称/ID。

`PACKAGE_VERSION`

要删除的包的版本。

## <a name="options"></a>选项

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--force-english-output`

 使用固定的、基于英语的区域性强制运行应用程序。

`-h|--help`

打印出有关命令的简短帮助。

`-k|--api-key <API_KEY>`

服务器的 API 密钥。

`--no-service-endpoint` 不将“api/v2/package”追加至源 URL。

`--non-interactive`

不提示用户输入或确认。

`-s|--source <SOURCE>`

指定服务器 URL。 Nuget.org 的支持 URL 包括 `https://www.nuget.org`、`https://www.nuget.org/api/v3` 和 `https://www.nuget.org/api/v2/package`。 对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--force-english-output`

 使用固定的、基于英语的区域性强制运行应用程序。

`-h|--help`

打印出有关命令的简短帮助。

`-k|--api-key <API_KEY>`

服务器的 API 密钥。

`--non-interactive`

不提示用户输入或确认。

`-s|--source <SOURCE>`

指定服务器 URL。 Nuget.org 的支持 URL 包括 `https://www.nuget.org`、`https://www.nuget.org/api/v3` 和 `https://www.nuget.org/api/v2/package`。 对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--force-english-output`

 使用固定的、基于英语的区域性强制运行应用程序。

`-h|--help`

打印出有关命令的简短帮助。

`-k|--api-key <API_KEY>`

服务器的 API 密钥。

`--non-interactive`

不提示用户输入或确认。

`-s|--source <SOURCE>`

指定服务器 URL。 Nuget.org 的支持 URL 包括 `https://www.nuget.org`、`https://www.nuget.org/api/v3` 和 `https://www.nuget.org/api/v2/package`。 对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。

---

## <a name="examples"></a>示例

删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版：

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0`

删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版（不提示用户需要凭据或其他输入）：

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`
