---
title: dotnet nuget push 命令
description: dotnet nuget push 命令可将包推送到服务器并发布。
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: d4ef8e58908fe488c712debff3b313ac0908b43e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503655"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="30a8d-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="30a8d-103">dotnet nuget push</span></span>

<span data-ttu-id="30a8d-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="30a8d-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="30a8d-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="30a8d-105">Name</span></span>

<span data-ttu-id="30a8d-106">`dotnet nuget push` - 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="30a8d-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="30a8d-107">摘要</span><span class="sxs-lookup"><span data-stu-id="30a8d-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [--skip-duplicate] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a><span data-ttu-id="30a8d-108">描述</span><span class="sxs-lookup"><span data-stu-id="30a8d-108">Description</span></span>

<span data-ttu-id="30a8d-109">`dotnet nuget push` 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="30a8d-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="30a8d-110">push 命令使用在系统的 NuGet 配置文件或配置文件链中找到的服务器和凭据详细信息。</span><span class="sxs-lookup"><span data-stu-id="30a8d-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="30a8d-111">有关配置文件的详细信息，请参阅 [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior)（配置 NuGet 行为）。</span><span class="sxs-lookup"><span data-stu-id="30a8d-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="30a8d-112">通过加载 *%AppData%\NuGet\NuGet.config* (Windows) 或 *$HOME/.local/share* (Linux/macOS) 获得 NuGet 的默认配置，然后加载任意 *nuget.config* 或 *.nuget\nuget.config*，从驱动器的根目录开始，并在当前目录中结束。</span><span class="sxs-lookup"><span data-stu-id="30a8d-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="30a8d-113">自变量</span><span class="sxs-lookup"><span data-stu-id="30a8d-113">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="30a8d-114">指定要推送的包的文件路径。</span><span class="sxs-lookup"><span data-stu-id="30a8d-114">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="30a8d-115">选项</span><span class="sxs-lookup"><span data-stu-id="30a8d-115">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="30a8d-116">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="30a8d-116">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="30a8d-117">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="30a8d-117">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="30a8d-118">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="30a8d-118">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="30a8d-119">对于身份验证等操作，允许命令阻止并要求手动操作。</span><span class="sxs-lookup"><span data-stu-id="30a8d-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="30a8d-120">自 .NET Core 2.2 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="30a8d-120">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="30a8d-121">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="30a8d-121">The API key for the server.</span></span>

- **`-n|--no-symbols`**

  <span data-ttu-id="30a8d-122">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="30a8d-122">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="30a8d-123">不将“api/v2/package”追加至源 URL。</span><span class="sxs-lookup"><span data-stu-id="30a8d-123">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="30a8d-124">自 .NET Core 2.1 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="30a8d-124">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="30a8d-125">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="30a8d-125">Specifies the server URL.</span></span> <span data-ttu-id="30a8d-126">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="30a8d-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="30a8d-127">将多个包推送到 HTTP(S) 服务器时，将任何 409 冲突响应视为警告，以便可以继续推送。</span><span class="sxs-lookup"><span data-stu-id="30a8d-127">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="30a8d-128">自 .NET Core 3.1 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="30a8d-128">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="30a8d-129">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="30a8d-129">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="30a8d-130">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="30a8d-130">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="30a8d-131">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="30a8d-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="30a8d-132">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="30a8d-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="30a8d-133">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="30a8d-133">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="30a8d-134">示例</span><span class="sxs-lookup"><span data-stu-id="30a8d-134">Examples</span></span>

- <span data-ttu-id="30a8d-135">将 foo.nupkg 推送到默认推送源（指定 API 密钥）  ：</span><span class="sxs-lookup"><span data-stu-id="30a8d-135">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="30a8d-136">将 foo.nupkg  推送到官方 NuGet 服务器，以指定 API 密钥：</span><span class="sxs-lookup"><span data-stu-id="30a8d-136">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="30a8d-137">将 foo.nupkg 推送到自定义推送源 `https://customsource`（指定 API 密钥）  ：</span><span class="sxs-lookup"><span data-stu-id="30a8d-137">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="30a8d-138">将 *foo.nupkg* 推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="30a8d-138">Pushes *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="30a8d-139">将 *foo.symbols.nupkg* 推送到默认符号源：</span><span class="sxs-lookup"><span data-stu-id="30a8d-139">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="30a8d-140">将 foo.nupkg 推送到默认推送源（指定 360 秒超时时间）  ：</span><span class="sxs-lookup"><span data-stu-id="30a8d-140">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="30a8d-141">将当前目录中的所有 *.nupkg* 文件推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="30a8d-141">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > <span data-ttu-id="30a8d-142">如果此命令不起作用，则可能是较旧版本的 SDK（.NET Core 2.1 SDK 及更早版本）中的 bug 导致的。</span><span class="sxs-lookup"><span data-stu-id="30a8d-142">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="30a8d-143">要解决此问题，请升级 SDK 版本或改为运行以下命令：`dotnet nuget push **/*.nupkg`</span><span class="sxs-lookup"><span data-stu-id="30a8d-143">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

- <span data-ttu-id="30a8d-144">推送所有 .nupkg 文件，即使 HTTP(S) 服务器返回了 409 冲突响应也是如此  ：</span><span class="sxs-lookup"><span data-stu-id="30a8d-144">Pushes all *.nupkg* files even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```
