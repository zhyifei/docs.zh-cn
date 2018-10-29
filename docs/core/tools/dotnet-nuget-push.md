---
title: dotnet nuget push 命令 - .NET Core CLI
description: dotnet nuget push 命令可将包推送到服务器并发布。
author: karann-msft
ms.author: mairaw
ms.date: 09/04/2018
ms.openlocfilehash: b9c0fad886cd1234325c58bf61b1a010bce421d9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "50200015"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="d6a35-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="d6a35-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d6a35-104">name</span><span class="sxs-lookup"><span data-stu-id="d6a35-104">Name</span></span>

<span data-ttu-id="d6a35-105">`dotnet nuget push` - 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="d6a35-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d6a35-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d6a35-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d6a35-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d6a35-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d6a35-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d6a35-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d6a35-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d6a35-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d6a35-110">描述</span><span class="sxs-lookup"><span data-stu-id="d6a35-110">Description</span></span>

<span data-ttu-id="d6a35-111">`dotnet nuget push` 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="d6a35-111">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="d6a35-112">push 命令使用在系统的 NuGet 配置文件或配置文件链中找到的服务器和凭据详细信息。</span><span class="sxs-lookup"><span data-stu-id="d6a35-112">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="d6a35-113">有关配置文件的详细信息，请参阅 [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior)（配置 NuGet 行为）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-113">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="d6a35-114">通过加载 *%AppData%\NuGet\NuGet.config* (Windows) 或 *$HOME/.local/share* (Linux/macOS) 获得 NuGet 的默认配置，然后加载任意 *nuget.config* 或 *.nuget\nuget.config*，从驱动器的根目录开始，并在当前目录中结束。</span><span class="sxs-lookup"><span data-stu-id="d6a35-114">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="d6a35-115">自变量</span><span class="sxs-lookup"><span data-stu-id="d6a35-115">Arguments</span></span>

`ROOT`

<span data-ttu-id="d6a35-116">指定要推送的包的文件路径。</span><span class="sxs-lookup"><span data-stu-id="d6a35-116">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="d6a35-117">选项</span><span class="sxs-lookup"><span data-stu-id="d6a35-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d6a35-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d6a35-118">.NET Core 2.1</span></span>](#tab/netcore21)

`-d|--disable-buffering`

<span data-ttu-id="d6a35-119">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="d6a35-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="d6a35-120">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d6a35-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="d6a35-121">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d6a35-121">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="d6a35-122">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d6a35-122">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="d6a35-123">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-123">Doesn't push symbols (even if present).</span></span>

`--no-service-endpoint`

<span data-ttu-id="d6a35-124">不将“api/v2/package”追加至源 URL。</span><span class="sxs-lookup"><span data-stu-id="d6a35-124">Doesn't append "api/v2/package" to the source URL.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="d6a35-125">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d6a35-125">Specifies the server URL.</span></span> <span data-ttu-id="d6a35-126">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="d6a35-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="d6a35-127">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d6a35-127">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="d6a35-128">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d6a35-128">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="d6a35-129">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="d6a35-130">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="d6a35-131">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="d6a35-131">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d6a35-132">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d6a35-132">.NET Core 2.0</span></span>](#tab/netcore20)

`-d|--disable-buffering`

<span data-ttu-id="d6a35-133">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="d6a35-133">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="d6a35-134">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d6a35-134">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="d6a35-135">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d6a35-135">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="d6a35-136">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d6a35-136">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="d6a35-137">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-137">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="d6a35-138">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d6a35-138">Specifies the server URL.</span></span> <span data-ttu-id="d6a35-139">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="d6a35-139">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="d6a35-140">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d6a35-140">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="d6a35-141">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d6a35-141">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="d6a35-142">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-142">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="d6a35-143">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-143">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="d6a35-144">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="d6a35-144">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d6a35-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d6a35-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`-d|--disable-buffering`

<span data-ttu-id="d6a35-146">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="d6a35-146">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="d6a35-147">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d6a35-147">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="d6a35-148">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d6a35-148">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="d6a35-149">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d6a35-149">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="d6a35-150">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-150">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="d6a35-151">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d6a35-151">Specifies the server URL.</span></span> <span data-ttu-id="d6a35-152">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="d6a35-152">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="d6a35-153">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d6a35-153">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="d6a35-154">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d6a35-154">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="d6a35-155">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-155">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="d6a35-156">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="d6a35-156">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="d6a35-157">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="d6a35-157">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d6a35-158">示例</span><span class="sxs-lookup"><span data-stu-id="d6a35-158">Examples</span></span>

<span data-ttu-id="d6a35-159">将 foo.nupkg 推送到默认推送源（指定 API 密钥）：</span><span class="sxs-lookup"><span data-stu-id="d6a35-159">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="d6a35-160">将 foo.nupkg 推送到自定义推送源 `https://customsource`（指定 API 密钥）：</span><span class="sxs-lookup"><span data-stu-id="d6a35-160">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/`

<span data-ttu-id="d6a35-161">将 *foo.nupkg* 推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="d6a35-161">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="d6a35-162">将 *foo.symbols.nupkg* 推送到默认符号源：</span><span class="sxs-lookup"><span data-stu-id="d6a35-162">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="d6a35-163">将 foo.nupkg 推送到默认推送源（指定 360 秒超时时间）：</span><span class="sxs-lookup"><span data-stu-id="d6a35-163">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="d6a35-164">将当前目录中的所有 *.nupkg* 文件推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="d6a35-164">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`
