---
title: dotnet nuget push 命令 - .NET Core CLI
description: dotnet nuget push 命令可将包推送到服务器并发布。
author: karann-msft
ms.author: mairaw
ms.date: 09/04/2018
ms.openlocfilehash: 23d27cef29008955850f9ed9f4a8baed9e7ad982
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45609987"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet nuget push` - 将包推送到服务器，并将其发布。

## <a name="synopsis"></a>摘要

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a>描述

`dotnet nuget push` 将包推送到服务器，并将其发布。 push 命令使用在系统的 NuGet 配置文件或配置文件链中找到的服务器和凭据详细信息。 有关配置文件的详细信息，请参阅 [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior)（配置 NuGet 行为）。 通过加载 *%AppData%\NuGet\NuGet.config* (Windows) 或 *$HOME/.local/share* (Linux/macOS) 获得 NuGet 的默认配置，然后加载任意 *nuget.config* 或 *.nuget\nuget.config*，从驱动器的根目录开始，并在当前目录中结束。

## <a name="arguments"></a>自变量

`ROOT`

指定要推送的包的文件路径。

## <a name="options"></a>选项

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`-d|--disable-buffering`

当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。

`--force-english-output`

使用固定的、基于英语的区域性强制运行应用程序。

`-h|--help`

打印出有关命令的简短帮助。

`-k|--api-key <API_KEY>`

服务器的 API 密钥。

`-n|--no-symbols`

不推送符号（即使存在）。

`--no-service-endpoint`

不将“api/v2/package”追加至源 URL。

`-s|--source <SOURCE>`

指定服务器 URL。 除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。

`-sk|--symbol-api-key <API_KEY>`

符号服务器的 API 密钥。

`-ss|--symbol-source <SOURCE>`

指定符号服务器 URL。

`-t|--timeout <TIMEOUT>`

指定推送到服务器的超时（秒）。 默认值为 300 秒（5 分钟）。 指定为 0（零秒）将应用默认值。

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`-d|--disable-buffering`

当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。

`--force-english-output`

使用固定的、基于英语的区域性强制运行应用程序。

`-h|--help`

打印出有关命令的简短帮助。

`-k|--api-key <API_KEY>`

服务器的 API 密钥。

`-n|--no-symbols`

不推送符号（即使存在）。

`-s|--source <SOURCE>`

指定服务器 URL。 除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。

`-sk|--symbol-api-key <API_KEY>`

符号服务器的 API 密钥。

`-ss|--symbol-source <SOURCE>`

指定符号服务器 URL。

`-t|--timeout <TIMEOUT>`

指定推送到服务器的超时（秒）。 默认值为 300 秒（5 分钟）。 指定为 0（零秒）将应用默认值。

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-d|--disable-buffering`

当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。

`--force-english-output`

使用固定的、基于英语的区域性强制运行应用程序。

`-h|--help`

打印出有关命令的简短帮助。

`-k|--api-key <API_KEY>`

服务器的 API 密钥。

`-n|--no-symbols`

不推送符号（即使存在）。

`-s|--source <SOURCE>`

指定服务器 URL。 除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。

`-sk|--symbol-api-key <API_KEY>`

符号服务器的 API 密钥。

`-ss|--symbol-source <SOURCE>`

指定符号服务器 URL。

`-t|--timeout <TIMEOUT>`

指定推送到服务器的超时（秒）。 默认值为 300 秒（5 分钟）。 指定为 0（零秒）将应用默认值。

---

## <a name="examples"></a>示例

将 foo.nupkg 推送到默认推送源（指定 API 密钥）：

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

将 foo.nupkg 推送到自定义推送源 `http://customsource`（指定 API 密钥）：

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

将 *foo.nupkg* 推送到默认推送源：

`dotnet nuget push foo.nupkg`

将 *foo.symbols.nupkg* 推送到默认符号源：

`dotnet nuget push foo.symbols.nupkg`

将 foo.nupkg 推送到默认推送源（指定 360 秒超时时间）：

`dotnet nuget push foo.nupkg --timeout 360`

将当前目录中的所有 *.nupkg* 文件推送到默认推送源：

`dotnet nuget push *.nupkg`
