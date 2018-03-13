---
title: "dotnet nuget push 命令 - .NET Core CLI"
description: "dotnet nuget push 命令可将包推送到服务器并发布。"
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: a0f872ae930d17638e018cdd204cc08a773a3df5
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="559ed-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="559ed-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="559ed-104">name</span><span class="sxs-lookup"><span data-stu-id="559ed-104">Name</span></span>

<span data-ttu-id="559ed-105">`dotnet nuget push` - 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="559ed-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="559ed-106">摘要</span><span class="sxs-lookup"><span data-stu-id="559ed-106">Synopsis</span></span>

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="559ed-107">描述</span><span class="sxs-lookup"><span data-stu-id="559ed-107">Description</span></span>

<span data-ttu-id="559ed-108">`dotnet nuget push` 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="559ed-108">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="559ed-109">push 命令使用在系统的 NuGet 配置文件或配置文件链中找到的服务器和凭据详细信息。</span><span class="sxs-lookup"><span data-stu-id="559ed-109">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="559ed-110">有关配置文件的详细信息，请参阅 [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior)（配置 NuGet 行为）。</span><span class="sxs-lookup"><span data-stu-id="559ed-110">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="559ed-111">通过加载 *%AppData%\NuGet\NuGet.config* (Windows) 或 *$HOME/.local/share* (Linux/macOS) 获得 NuGet 的默认配置，然后加载任意 *nuget.config* 或 *.nuget\nuget.config*，从驱动器的根目录开始，并在当前目录中结束。</span><span class="sxs-lookup"><span data-stu-id="559ed-111">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="559ed-112">自变量</span><span class="sxs-lookup"><span data-stu-id="559ed-112">Arguments</span></span>

`ROOT`

<span data-ttu-id="559ed-113">指定要推送的包的文件路径。</span><span class="sxs-lookup"><span data-stu-id="559ed-113">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="559ed-114">选项</span><span class="sxs-lookup"><span data-stu-id="559ed-114">Options</span></span>

`-h|--help`

<span data-ttu-id="559ed-115">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="559ed-115">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="559ed-116">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="559ed-116">Specifies the server URL.</span></span> <span data-ttu-id="559ed-117">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="559ed-117">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`--symbol-source <SOURCE>`

<span data-ttu-id="559ed-118">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="559ed-118">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="559ed-119">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="559ed-119">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="559ed-120">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="559ed-120">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="559ed-121">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="559ed-121">Specifying 0 (zero seconds) applies the default value.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="559ed-122">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="559ed-122">The API key for the server.</span></span>

`--symbol-api-key <API_KEY>`

<span data-ttu-id="559ed-123">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="559ed-123">The API key for the symbol server.</span></span>

`-d|--disable-buffering`

<span data-ttu-id="559ed-124">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="559ed-124">Disables buffering when pushing to an HTTP(S) server to decrease memory usage.</span></span>

`-n|--no-symbols`

<span data-ttu-id="559ed-125">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="559ed-125">Doesn't push symbols (even if present).</span></span>

`--force-english-output`

<span data-ttu-id="559ed-126">强制所有记录的输出以英语显示。</span><span class="sxs-lookup"><span data-stu-id="559ed-126">Forces all logged output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="559ed-127">示例</span><span class="sxs-lookup"><span data-stu-id="559ed-127">Examples</span></span>

<span data-ttu-id="559ed-128">将 *foo.nupkg* 推送到默认推送源（提供 API 密钥）：</span><span class="sxs-lookup"><span data-stu-id="559ed-128">Pushes *foo.nupkg* to the default push source, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="559ed-129">将 *foo.nupkg* 推送到自定义推送源 `http://customsource`（提供 API 密钥）：</span><span class="sxs-lookup"><span data-stu-id="559ed-129">Push *foo.nupkg* to the custom push source `http://customsource`, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="559ed-130">将 *foo.nupkg* 推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="559ed-130">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="559ed-131">将 *foo.symbols.nupkg* 推送到默认符号源：</span><span class="sxs-lookup"><span data-stu-id="559ed-131">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="559ed-132">将 *foo.nupkg* 推送到默认推送源（指定 360 秒超时时间）：</span><span class="sxs-lookup"><span data-stu-id="559ed-132">Pushes *foo.nupkg* to the default push source, specifying a 360 second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="559ed-133">将当前目录中的所有 *.nupkg* 文件推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="559ed-133">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="559ed-134">将当前目录中的所有 *.nupkg* 文件推送到默认推送源（指定自定义配置文件 *./config/My.Config*）：</span><span class="sxs-lookup"><span data-stu-id="559ed-134">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`
