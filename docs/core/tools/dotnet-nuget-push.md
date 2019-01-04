---
title: dotnet nuget push 命令
description: dotnet nuget push 命令可将包推送到服务器并发布。
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 4f0d127d8b9f37b1c381d8981f54035a2fc3b0e5
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169347"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="d7c71-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="d7c71-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d7c71-104">name</span><span class="sxs-lookup"><span data-stu-id="d7c71-104">Name</span></span>

<span data-ttu-id="d7c71-105">`dotnet nuget push` - 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="d7c71-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d7c71-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d7c71-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d7c71-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d7c71-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d7c71-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d7c71-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d7c71-109">说明</span><span class="sxs-lookup"><span data-stu-id="d7c71-109">Description</span></span>

<span data-ttu-id="d7c71-110">`dotnet nuget push` 将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="d7c71-110">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="d7c71-111">push 命令使用在系统的 NuGet 配置文件或配置文件链中找到的服务器和凭据详细信息。</span><span class="sxs-lookup"><span data-stu-id="d7c71-111">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="d7c71-112">有关配置文件的详细信息，请参阅 [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior)（配置 NuGet 行为）。</span><span class="sxs-lookup"><span data-stu-id="d7c71-112">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="d7c71-113">通过加载 *%AppData%\NuGet\NuGet.config* (Windows) 或 *$HOME/.local/share* (Linux/macOS) 获得 NuGet 的默认配置，然后加载任意 *nuget.config* 或 *.nuget\nuget.config*，从驱动器的根目录开始，并在当前目录中结束。</span><span class="sxs-lookup"><span data-stu-id="d7c71-113">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="d7c71-114">自变量</span><span class="sxs-lookup"><span data-stu-id="d7c71-114">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="d7c71-115">指定要推送的包的文件路径。</span><span class="sxs-lookup"><span data-stu-id="d7c71-115">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="d7c71-116">选项</span><span class="sxs-lookup"><span data-stu-id="d7c71-116">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d7c71-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d7c71-117">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="d7c71-118">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="d7c71-118">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="d7c71-119">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7c71-119">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

<span data-ttu-id="d7c71-120">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d7c71-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="d7c71-121">对于身份验证等操作，允许命令阻止并要求手动操作。</span><span class="sxs-lookup"><span data-stu-id="d7c71-121">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="d7c71-122">自 .NET Core 2.2 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="d7c71-122">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="d7c71-123">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d7c71-123">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="d7c71-124">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="d7c71-124">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="d7c71-125">不将“api/v2/package”追加至源 URL。</span><span class="sxs-lookup"><span data-stu-id="d7c71-125">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="d7c71-126">自 .NET Core 2.1 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="d7c71-126">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="d7c71-127">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d7c71-127">Specifies the server URL.</span></span> <span data-ttu-id="d7c71-128">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="d7c71-128">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="d7c71-129">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d7c71-129">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="d7c71-130">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d7c71-130">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="d7c71-131">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="d7c71-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="d7c71-132">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="d7c71-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="d7c71-133">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="d7c71-133">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d7c71-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d7c71-134">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="d7c71-135">当推送到 HTTP(S) 服务器以减少内存使用率时，禁用缓冲。</span><span class="sxs-lookup"><span data-stu-id="d7c71-135">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="d7c71-136">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7c71-136">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="d7c71-137">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d7c71-137">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="d7c71-138">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d7c71-138">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="d7c71-139">不推送符号（即使存在）。</span><span class="sxs-lookup"><span data-stu-id="d7c71-139">Doesn't push symbols (even if present).</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="d7c71-140">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d7c71-140">Specifies the server URL.</span></span> <span data-ttu-id="d7c71-141">除非在 NuGet 配置文件中设置了 `DefaultPushSource` 配置值，否则此选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="d7c71-141">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="d7c71-142">符号服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="d7c71-142">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="d7c71-143">指定符号服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="d7c71-143">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="d7c71-144">指定推送到服务器的超时（秒）。</span><span class="sxs-lookup"><span data-stu-id="d7c71-144">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="d7c71-145">默认值为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="d7c71-145">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="d7c71-146">指定为 0（零秒）将应用默认值。</span><span class="sxs-lookup"><span data-stu-id="d7c71-146">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d7c71-147">示例</span><span class="sxs-lookup"><span data-stu-id="d7c71-147">Examples</span></span>

* <span data-ttu-id="d7c71-148">将 foo.nupkg 推送到默认推送源（指定 API 密钥）：</span><span class="sxs-lookup"><span data-stu-id="d7c71-148">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="d7c71-149">将 foo.nupkg 推送到自定义推送源 `https://customsource`（指定 API 密钥）：</span><span class="sxs-lookup"><span data-stu-id="d7c71-149">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="d7c71-150">将 *foo.nupkg* 推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="d7c71-150">Pushes *foo.nupkg* to the default push source:</span></span>

  ```console
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="d7c71-151">将 *foo.symbols.nupkg* 推送到默认符号源：</span><span class="sxs-lookup"><span data-stu-id="d7c71-151">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="d7c71-152">将 foo.nupkg 推送到默认推送源（指定 360 秒超时时间）：</span><span class="sxs-lookup"><span data-stu-id="d7c71-152">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="d7c71-153">将当前目录中的所有 *.nupkg* 文件推送到默认推送源：</span><span class="sxs-lookup"><span data-stu-id="d7c71-153">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```console
  dotnet nuget push *.nupkg
  ```