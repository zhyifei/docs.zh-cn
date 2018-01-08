---
title: "dotnet nuget delete 命令 - .NET Core CLI"
description: "dotnet-nuget-delete 命令从服务器删除或取消列出包。"
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 3c09556fe90a5c447b181bc1ac5b36f014399e4f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="502a9-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="502a9-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="502a9-104">name</span><span class="sxs-lookup"><span data-stu-id="502a9-104">Name</span></span>

<span data-ttu-id="502a9-105">`dotnet nuget delete` - 从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="502a9-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="502a9-106">摘要</span><span class="sxs-lookup"><span data-stu-id="502a9-106">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="502a9-107">描述</span><span class="sxs-lookup"><span data-stu-id="502a9-107">Description</span></span>

<span data-ttu-id="502a9-108">`dotnet nuget delete` 命令从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="502a9-108">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="502a9-109">对于 [NuGet.org](https://www.nuget.org/)，该操作将取消列出包。</span><span class="sxs-lookup"><span data-stu-id="502a9-109">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="502a9-110">自变量</span><span class="sxs-lookup"><span data-stu-id="502a9-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="502a9-111">要删除的包。</span><span class="sxs-lookup"><span data-stu-id="502a9-111">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="502a9-112">要删除的包的版本。</span><span class="sxs-lookup"><span data-stu-id="502a9-112">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="502a9-113">选项</span><span class="sxs-lookup"><span data-stu-id="502a9-113">Options</span></span>

`-h|--help`

<span data-ttu-id="502a9-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="502a9-114">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="502a9-115">指定服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="502a9-115">Specifies the server URL.</span></span> <span data-ttu-id="502a9-116">Nuget.org 的支持 URL 包括 `http://www.nuget.org`、`http://www.nuget.org/api/v3` 和 `http://www.nuget.org/api/v2/package`。</span><span class="sxs-lookup"><span data-stu-id="502a9-116">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="502a9-117">对于专用源，请替换主机名（例如，`%hostname%/api/v3`）。</span><span class="sxs-lookup"><span data-stu-id="502a9-117">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="502a9-118">不提示用户输入或确认。</span><span class="sxs-lookup"><span data-stu-id="502a9-118">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="502a9-119">服务器的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="502a9-119">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="502a9-120">强制命令行输出以英语显示。</span><span class="sxs-lookup"><span data-stu-id="502a9-120">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="502a9-121">示例</span><span class="sxs-lookup"><span data-stu-id="502a9-121">Examples</span></span>

<span data-ttu-id="502a9-122">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版：</span><span class="sxs-lookup"><span data-stu-id="502a9-122">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="502a9-123">删除包 `Microsoft.AspNetCore.Mvc` 的 1.0 版（不提示用户需要凭据或其他输入）：</span><span class="sxs-lookup"><span data-stu-id="502a9-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`