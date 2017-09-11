---
title: "dotnet-nuget-delete 命令 - .NET Core CLI"
description: "dotnet-nuget-delete 命令从服务器删除或取消列出包。"
keywords: "dotnet-nuget-delete, CLI, CLI 命令, .NET Core"
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce6886f2f4cc8cc633cfc61215fe17550f746c91
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-delete"></a><span data-ttu-id="56da1-104">dotnet-nuget delete</span><span class="sxs-lookup"><span data-stu-id="56da1-104">dotnet-nuget delete</span></span>

## <a name="name"></a><span data-ttu-id="56da1-105">名称</span><span class="sxs-lookup"><span data-stu-id="56da1-105">Name</span></span>

<span data-ttu-id="56da1-106">`dotnet-nuget-delete` - 从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="56da1-106">`dotnet-nuget-delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="56da1-107">摘要</span><span class="sxs-lookup"><span data-stu-id="56da1-107">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="56da1-108">描述</span><span class="sxs-lookup"><span data-stu-id="56da1-108">Description</span></span>

<span data-ttu-id="56da1-109">`dotnet nuget delete` 命令从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="56da1-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="56da1-110">对于 [NuGet.org](https://www.nuget.org/)，该操作将取消列出包。</span><span class="sxs-lookup"><span data-stu-id="56da1-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="56da1-111">参数</span><span class="sxs-lookup"><span data-stu-id="56da1-111">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="56da1-112">要删除的包。</span><span class="sxs-lookup"><span data-stu-id="56da1-112">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="56da1-113">要删除的包的版本。</span><span class="sxs-lookup"><span data-stu-id="56da1-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="56da1-114">选项</span><span class="sxs-lookup"><span data-stu-id="56da1-114">Options</span></span>

`-h|--help`

<span data-ttu-id="56da1-115">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="56da1-115">Prints out a short help for the command.</span></span>  

`-s|--source <SOURCE>`

<span data-ttu-id="56da1-116">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="56da1-116">Specifies the server URL.</span></span> <span data-ttu-id="56da1-117">Nuget.org 的支持 URL 包括 `http://www.nuget.org`、`http://www.nuget.org/api/v3` 和 `http://www.nuget.org/api/v2/package`。</span><span class="sxs-lookup"><span data-stu-id="56da1-117">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="56da1-118">对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。</span><span class="sxs-lookup"><span data-stu-id="56da1-118">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="56da1-119">不提示用户输入或确认。</span><span class="sxs-lookup"><span data-stu-id="56da1-119">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="56da1-120">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="56da1-120">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="56da1-121">强制命令行输出以英语显示。</span><span class="sxs-lookup"><span data-stu-id="56da1-121">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="56da1-122">示例</span><span class="sxs-lookup"><span data-stu-id="56da1-122">Examples</span></span>

<span data-ttu-id="56da1-123">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版：</span><span class="sxs-lookup"><span data-stu-id="56da1-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="56da1-124">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版（不提示用户需要凭据或其他输入）：</span><span class="sxs-lookup"><span data-stu-id="56da1-124">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`

