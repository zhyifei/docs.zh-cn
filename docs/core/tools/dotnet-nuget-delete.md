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
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="2bc6e-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="2bc6e-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2bc6e-104">name</span><span class="sxs-lookup"><span data-stu-id="2bc6e-104">Name</span></span>

<span data-ttu-id="2bc6e-105">`dotnet nuget delete` - 从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2bc6e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="2bc6e-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2bc6e-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2bc6e-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2bc6e-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2bc6e-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2bc6e-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2bc6e-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="2bc6e-110">描述</span><span class="sxs-lookup"><span data-stu-id="2bc6e-110">Description</span></span>

<span data-ttu-id="2bc6e-111">`dotnet nuget delete` 命令从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-111">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="2bc6e-112">对于 [NuGet.org](https://www.nuget.org/)，该操作将取消列出包。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-112">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="2bc6e-113">自变量</span><span class="sxs-lookup"><span data-stu-id="2bc6e-113">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="2bc6e-114">要删除的包的名称/ID。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-114">Name/ID of the package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="2bc6e-115">要删除的包的版本。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-115">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="2bc6e-116">选项</span><span class="sxs-lookup"><span data-stu-id="2bc6e-116">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2bc6e-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2bc6e-117">.NET Core 2.1</span></span>](#tab/netcore21)

`--force-english-output`

 <span data-ttu-id="2bc6e-118">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-118">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="2bc6e-119">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-119">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="2bc6e-120">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-120">The API key for the server.</span></span>

<span data-ttu-id="2bc6e-121">`--no-service-endpoint` 不将“api/v2/package”追加至源 URL。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-121">`--no-service-endpoint` Doesn't append "api/v2/package" to the source URL.</span></span>

`--non-interactive`

<span data-ttu-id="2bc6e-122">不提示用户输入或确认。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-122">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="2bc6e-123">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-123">Specifies the server URL.</span></span> <span data-ttu-id="2bc6e-124">Nuget.org 的支持 URL 包括 `https://www.nuget.org`、`https://www.nuget.org/api/v3` 和 `https://www.nuget.org/api/v2/package`。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="2bc6e-125">对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2bc6e-126">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2bc6e-126">.NET Core 2.0</span></span>](#tab/netcore20)

`--force-english-output`

 <span data-ttu-id="2bc6e-127">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-127">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="2bc6e-128">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-128">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="2bc6e-129">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-129">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="2bc6e-130">不提示用户输入或确认。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-130">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="2bc6e-131">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-131">Specifies the server URL.</span></span> <span data-ttu-id="2bc6e-132">Nuget.org 的支持 URL 包括 `https://www.nuget.org`、`https://www.nuget.org/api/v3` 和 `https://www.nuget.org/api/v2/package`。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-132">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="2bc6e-133">对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-133">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2bc6e-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2bc6e-134">.NET Core 1.x</span></span>](#tab/netcore1x)

`--force-english-output`

 <span data-ttu-id="2bc6e-135">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-135">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="2bc6e-136">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-136">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="2bc6e-137">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-137">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="2bc6e-138">不提示用户输入或确认。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-138">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="2bc6e-139">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-139">Specifies the server URL.</span></span> <span data-ttu-id="2bc6e-140">Nuget.org 的支持 URL 包括 `https://www.nuget.org`、`https://www.nuget.org/api/v3` 和 `https://www.nuget.org/api/v2/package`。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-140">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="2bc6e-141">对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。</span><span class="sxs-lookup"><span data-stu-id="2bc6e-141">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="2bc6e-142">示例</span><span class="sxs-lookup"><span data-stu-id="2bc6e-142">Examples</span></span>

<span data-ttu-id="2bc6e-143">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版：</span><span class="sxs-lookup"><span data-stu-id="2bc6e-143">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0`

<span data-ttu-id="2bc6e-144">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版（不提示用户需要凭据或其他输入）：</span><span class="sxs-lookup"><span data-stu-id="2bc6e-144">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`
