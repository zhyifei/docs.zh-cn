---
title: dotnet nuget push 命令 - .NET Core CLI
description: dotnet nuget push 命令可将包推送到服务器并发布。
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: 8a64f9cdc11d03bed82a132265c3b4e1de290807
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728571"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="384cc-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="384cc-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="384cc-104">name</span><span class="sxs-lookup"><span data-stu-id="384cc-104">Name</span></span>

<span data-ttu-id="384cc-105">`dotnet nuget push` - 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="384cc-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="384cc-106">摘要</span><span class="sxs-lookup"><span data-stu-id="384cc-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="384cc-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="384cc-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="384cc-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="384cc-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="384cc-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="384cc-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="384cc-110">描述</span><span class="sxs-lookup"><span data-stu-id="384cc-110">Description</span></span>

<span data-ttu-id="384cc-111">`dotnet nuget push` 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="384cc-111">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="384cc-112">push 命令使用在系统的 NuGet 配置文件或配置文件链中找到的服务器和凭据详细信息。</span><span class="sxs-lookup"><span data-stu-id="384cc-112">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="384cc-113">有关配置文件的详细信息，请参阅 [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior)（配置 NuGet 行为）。</span><span class="sxs-lookup"><span data-stu-id="384cc-113">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="384cc-114">通过加载 *%AppData%\NuGet\NuGet.config* (Windows) 或 *$HOME/.local/share* (Linux/macOS) 获得 NuGet 的默认配置，然后加载任意 *nuget.config* 或 *.nuget\nuget.config*，从驱动器的根目录开始，并在当前目录中结束。</span><span class="sxs-lookup"><span data-stu-id="384cc-114">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="384cc-115">自变量</span><span class="sxs-lookup"><span data-stu-id="384cc-115">Arguments</span></span>

`ROOT`

<span data-ttu-id="384cc-116">指定要推送的包的文件路径。</span><span class="sxs-lookup"><span data-stu-id="384cc-116">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="384cc-117">选项</span><span class="sxs-lookup"><span data-stu-id="384cc-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="384cc-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="384cc-118">.NET Core 2.1</span></span>](#tab/netcore21)

`-d|--disable-buffering`

<span data-ttu-id="384cc-119">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="384cc-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="384cc-120">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="384cc-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="384cc-121">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="384cc-121">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="384cc-122">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="384cc-122">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="384cc-123">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="384cc-123">Doesn't push symbols (even if present).</span></span>

`--no-service-endpoint`

<span data-ttu-id="384cc-124">不将“api/v2/package”追加至源 URL。</span><span class="sxs-lookup"><span data-stu-id="384cc-124">Doesn't append "api/v2/package" to the source URL.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="384cc-125">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="384cc-125">Specifies the server URL.</span></span> <span data-ttu-id="384cc-126">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="384cc-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="384cc-127">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="384cc-127">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="384cc-128">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="384cc-128">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="384cc-129">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="384cc-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="384cc-130">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="384cc-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="384cc-131">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="384cc-131">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="384cc-132">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="384cc-132">.NET Core 2.0</span></span>](#tab/netcore20)

`-d|--disable-buffering`

<span data-ttu-id="384cc-133">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="384cc-133">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="384cc-134">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="384cc-134">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="384cc-135">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="384cc-135">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="384cc-136">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="384cc-136">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="384cc-137">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="384cc-137">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="384cc-138">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="384cc-138">Specifies the server URL.</span></span> <span data-ttu-id="384cc-139">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="384cc-139">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="384cc-140">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="384cc-140">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="384cc-141">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="384cc-141">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="384cc-142">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="384cc-142">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="384cc-143">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="384cc-143">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="384cc-144">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="384cc-144">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="384cc-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="384cc-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`-d|--disable-buffering`

<span data-ttu-id="384cc-146">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="384cc-146">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="384cc-147">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="384cc-147">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="384cc-148">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="384cc-148">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="384cc-149">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="384cc-149">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="384cc-150">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="384cc-150">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="384cc-151">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="384cc-151">Specifies the server URL.</span></span> <span data-ttu-id="384cc-152">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="384cc-152">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="384cc-153">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="384cc-153">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="384cc-154">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="384cc-154">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="384cc-155">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="384cc-155">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="384cc-156">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="384cc-156">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="384cc-157">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="384cc-157">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="384cc-158">示例</span><span class="sxs-lookup"><span data-stu-id="384cc-158">Examples</span></span>

<span data-ttu-id="384cc-159">将 foo.nupkg 推送到默认推送源（指定 API 密钥）：</span><span class="sxs-lookup"><span data-stu-id="384cc-159">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="384cc-160">将 foo.nupkg 推送到自定义推送源 `http://customsource`（指定 API 密钥）：</span><span class="sxs-lookup"><span data-stu-id="384cc-160">Push *foo.nupkg* to the custom push source `http://customsource`, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="384cc-161">将 *foo.nupkg* 推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="384cc-161">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="384cc-162">将 *foo.symbols.nupkg* 推送到默认符号源：</span><span class="sxs-lookup"><span data-stu-id="384cc-162">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="384cc-163">将 foo.nupkg 推送到默认推送源（指定 360 秒超时时间）：</span><span class="sxs-lookup"><span data-stu-id="384cc-163">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="384cc-164">将当前目录中的所有 *.nupkg* 文件推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="384cc-164">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="384cc-165">将当前目录中的所有 *.nupkg* 文件推送到默认推送源（指定自定义配置文件 *./config/My.Config*）：</span><span class="sxs-lookup"><span data-stu-id="384cc-165">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`
