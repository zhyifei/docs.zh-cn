---
title: dotnet nuget push 命令
description: dotnet nuget push 命令可将包推送到服务器并发布。
author: karann-msft
ms.date: 12/04/2019
ms.openlocfilehash: 5e80295a570adc30a06d86b6735cb0387e39d5a3
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74835514"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**本主题适用于：✓** .NET Core 1.x SDK 及更高版本

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>名称

`dotnet nuget push` - 将包推送到服务器，并将其发布。

## <a name="synopsis"></a>摘要

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [--skip-duplicate] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a>说明

`dotnet nuget push` 将包推送到服务器，并将其发布。 push 命令使用在系统的 NuGet 配置文件或配置文件链中找到的服务器和凭据详细信息。 有关配置文件的详细信息，请参阅 [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior)（配置 NuGet 行为）。 通过加载 *%AppData%\NuGet\NuGet.config* (Windows) 或 *$HOME/.local/share* (Linux/macOS) 获得 NuGet 的默认配置，然后加载任意 *nuget.config* 或 *.nuget\nuget.config*，从驱动器的根目录开始，并在当前目录中结束。

## <a name="arguments"></a>自变量

* **`ROOT`**

  指定要推送的包的文件路径。

## <a name="options"></a>选项

* **`-d|--disable-buffering`**

  当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。

* **`--force-english-output`**

  使用固定的、基于英语的区域性强制运行应用程序。

* **`-h|--help`**

  打印出有关命令的简短帮助。

* **`--interactive`**

  对于身份验证等操作，允许命令阻止并要求手动操作。 自 .NET Core 2.2 SDK 起可用的选项。

* **`-k|--api-key <API_KEY>`**

  服务器的 API 密钥。

* **`-n|--no-symbols`**

  不推送符号（即使存在）。

* **`--no-service-endpoint`**

  不将“api/v2/package”追加至源 URL。 自 .NET Core 2.1 SDK 起可用的选项。

* **`-s|--source <SOURCE>`**

  指定服务器 URL。 除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。

* **`--skip-duplicate`**

  将多个包推送到 HTTP(S) 服务器时，将任何 409 冲突响应视为警告，以便可以继续推送。 自 .NET Core 3.1 SDK 起可用。
                                 
* **`-sk|--symbol-api-key <API_KEY>`**

  符号服务器的 API 密钥。

* **`-ss|--symbol-source <SOURCE>`**

  指定符号服务器 URL。

* **`-t|--timeout <TIMEOUT>`**

  指定推送到服务器的超时（秒）。 默认值为 300 秒（5 分钟）。 指定为 0（零秒）将应用默认值。

## <a name="examples"></a>示例

* 将 foo.nupkg 推送到默认推送源（指定 API 密钥）  ：

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* 将 foo.nupkg 推送到自定义推送源 `https://customsource`（指定 API 密钥）  ：

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* 将 *foo.nupkg* 推送到默认推送源：

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

* 将 *foo.symbols.nupkg* 推送到默认符号源：

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

* 将 foo.nupkg 推送到默认推送源（指定 360 秒超时时间）  ：

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

* 将当前目录中的所有 *.nupkg* 文件推送到默认推送源：

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```
  
  > [!NOTE]
  > 如果此命令不起作用，则可能是较旧版本的 SDK（.NET Core 2.1 SDK 及更早版本）中的 bug 导致的。
  > 要解决此问题，请升级 SDK 版本或改为运行以下命令：`dotnet nuget push **/*.nupkg`
  
* 推送所有 .nupkg 文件，即使 HTTP(S) 服务器返回了 409 冲突响应也是如此  ：

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```
